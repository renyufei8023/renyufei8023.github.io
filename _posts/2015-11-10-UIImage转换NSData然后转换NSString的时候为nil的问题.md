---
layout: post
title: UIImage转换NSData然后转换NSString的时候为nil的问题
author: 任玉飞
date: 2015.11.10 20:57:32 +0800
categories: Blog
tag: Blog
---

#UIImage转换NSData然后转换NSString的时候为nil的问题
今天在项目当中需要把UIImage转换成NSString，然后和普通的POST请求一样，把代码上传到服务器上面，刚开始后台返回success，然后让php人员看了下是否成功了，然后他那边显示是没有的。于是我自己打断点调试看了下，转换后的字符串为nil，后来经过搜索说是编码的问题，然后换了一种编码也还是不行，最后找到了这个方法，虽说不是什么技术性问题，但也有记录下的必要，以免以后忘记。

	//图片转字符串  
	-(NSString *)UIImageToBase64Str:(UIImage *) image  
	{  
    NSData *data = UIImageJPEGRepresentation(image, 1.0f);  
    NSString *encodedImageStr = [data base64EncodedStringWithOptions:NSDataBase64Encoding64CharacterLineLength];  
    return encodedImageStr;  
	}  
	
	//字符串转图片  
	-(UIImage *)Base64StrToUIImage:(NSString *)_encodedImageStr  
	{  
    	NSData *_decodedImageData   = [[NSData alloc] initWithBase64Encoding:_encodedImageStr];  
    	UIImage *_decodedImage      = [UIImage imageWithData:_decodedImageData];  
    	return _decodedImage;  
	}

11月11日更新，今天在浏览博客的时候看到了这样的一种解决方案，也是因为编码问题转换的时候返回nil，该作者是对NSData写了一个分类，具体实现如下：
      


	@implementation NSData (UTF8)

	- (NSData *)UTF8Data
	{
    	//保存结果
    	NSMutableData *resData = [[NSMutableData alloc] initWithCapacity:self.length];
    
    	//无效编码替代符号(常见 � □ ?)
    	NSData *replacement = [@"�" dataUsingEncoding:NSUTF8StringEncoding];
    
    	uint64_t index = 0;
    	const uint8_t *bytes = self.bytes;
    
    	while (index < self.length)
    	{
        	uint8_t len = 0;
        	uint8_t header = bytes[index];
        
        	//单字节
        	if ((header&0x80) == 0)
        	{
            	len = 1;
        	}
        	//2字节(并且不能为C0,C1)
        	else if ((header&0xE0) == 0xC0)
        	{
            	if (header != 0xC0 && header != 0xC1)
            	{
                	len = 2;
            	}
        	}
        	//3字节
        	else if((header&0xF0) == 0xE0)
        	{
            	len = 3;
        	}
        	//4字节(并且不能为F5,F6,F7)
        	else if ((header&0xF8) == 0xF0)
        	{
            	if (header != 0xF5 && header != 0xF6 && header != 0xF7)
            	{
                	len = 4;
            	}
        	}
        
        	//无法识别
        	if (len == 0)
        	{
            	[resData appendData:replacement];
            	index++;
            	continue;
        	}
        
        	//检测有效的数据长度(后面还有多少个10xxxxxx这样的字节)
        	uint8_t validLen = 1;
        	while (validLen < len && index+validLen < self.length)
        	{
            	if ((bytes[index+validLen] & 0xC0) != 0x80)
                	break;
            	validLen++;
        	}
        
        	//有效字节等于编码要求的字节数表示合法,否则不合法
        	if (validLen == len)
        	{
            	[resData appendBytes:bytes+index length:len];
        	}else
        	{
            	[resData appendData:replacement];
        	}
        
        	//移动下标
        	index += validLen;
    	}
    
    	return resData;
	}

	@end
<a href="http://www.tanhao.me/code/150608.html/" target="_blank">来源</a>

