# 使用selenium控制已经运行的浏览器

1. 以谷歌浏览器为例,找到浏览器的目录,将其添加到环境变量中

2. `"Google Chrome" --remote-debugging-port=9222'`命令启动浏览器

3. selenium的浏览器对象创建

   ```
   options = Options()
   options.add_experimental_option("debuggerAddress", "127.0.0.1:9222")
   chr_obj = webdriver.Chrome(r'/Users/yaojiaqi/Desktop/notes/chromedriver', options=SpiderSelenium.options)
   ```

4. 使用上面的chr_obj就可以控制刚才打开的浏览器了



