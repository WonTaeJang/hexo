---
title: check a file exists at a URL(ASP.NET)
date: 2021-04-19 17:02:04
tags:
    - asp.net 
    - c#
    - request
    - response
    - web
    - http
categories: 
    - ASP.NET
---

web resource를 가져오기 전 HttpWebRequest Class를 이용하여 Head 정보만 가져온다. 

``` c#
string url = "https://www.domain.com/img/test.png";

WebRequest webRequest = WebRequest.Create(url);
webRequest.Method = "HEAD";

try
{
    using (HttpWebResponse response = (HttpWebResponse)webRequest.GetResponse()) 
    {
        if (response.StatusCode.ToString() == "OK")
        {
            //YOUR_CODE
        }
    }
}
catch(WebException ex)
{
    // error
}
finally
{
    // Don't forget to close your response
    if(response != null)
    {
        response.Close();
    }
}
```


추가로 일반적인 file path일 경우 

``` c#
if(File.Exist(path))
```