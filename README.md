# --
//1.通过某种途径(网络请求) 获得JSON数据
    
    NSURL *myURlL = [[ NSURL alloc]initWithString:@"https://api.github.com/user?access_token=8dc53c683f3f7410a21d6d85db6a9c14149612c6"];
    
    //这个JSON数据用NSData表示即可
    NSData *jsonData = [[NSData alloc]initWithContentsOfURL:myURlL];
    
    //2.把整个JSON数据转换成字典与数组的结构
    NSDictionary *jsonDict = [NSJSONSerialization JSONObjectWithData:jsonData options:0 error:nil];
    
    //3.按照层次结构进行解析
    
    //3.1.获取System_User键对应的数据
    NSArray *system_user = jsonDict[@"login"];
    
    NSLog(@"login:%@",system_user);
