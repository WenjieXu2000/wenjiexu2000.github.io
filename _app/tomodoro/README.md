# Tomodoro&nbsp;
A pomodoro web app with PIP mode, white noise generation, tasks and more!

## Features:

-   Clean UI
-   PIP Mode
-   Tasks and Statistics
-   White Noise
-   Themes
-   Works Offline

## Structure

```
├── icons
│   ├── appletouch.png          # 应用图标
│   ├── favicon.png             # 网站的小图标（favicon）
│   ├── icon.png                # 网站图标
│   ├── icon192.png             # 192x192 尺寸的图标
│   ├── icon512.png             # 512x512 尺寸的图标
│   ├── maskable_icon.png       # 可遮罩的图标
│   ├── maskable192.png         # 192x192 尺寸的可遮罩图标
│   ├── maskable512.png         # 512x512 尺寸的可遮罩图标
├── .gitattributes              # Git 属性文件
├── .gitignore                  # Git 忽略文件列表
├── GitHub-Mark-64px.png        # GitHub 标志图片
├── index.css                   # 主样式表文件
├── index.html                  # 主 HTML 文件
├── index.js                    # 主 JavaScript 文件
├── LICENSE.md                  # 项目许可证文件（MIT 许可证）
├── pip.png                     # PIP 模式的演示图片
├── README.md                   # 项目简介和说明文件
├── screenshot.png              # 应用截图
├── site.webmanifest            # Web 应用清单文件
├── statistics.png              # 统计功能演示图片
├── Str.txt                     # 未知用途的文本文件
├── sw.js                       # 服务工作者脚本，用于离线支持和缓存
└── worker.js                   # Web Worker 脚本
```

## Tasks and Statistics

Tomodoro allows the creation of "Tasks". Time spent in a focus session can be dedicated to a task in order to generate statistics.
All the data is saved in your browser. Taking frequent backups is recommended. Backup and restore options are available in Tomodoro's settings.

## About Always On Top/PIP Mode

**Not tested on Safari but might work**

PIP mode works by drawing on a canvas, capturing its stream and using it as source of a video element. Then it requests Picture-In-Picture.

On desktop Firefox, PIP button will only make the video visible but will not activate PIP. To switch to PIP mode, right click on the video and select "Watch in Picture-In-Picture".

On Android browsers, like Chrome for Android which does not support the Picture-In-Picture API, in order to switch to PIP mode, make the video fullscreen and then go to your device's homescreen without exiting fullscreen. If your browser is supported then PIP mode will be activated.

## To-Do

-   Make code cleaner
-   Add custom theming


## Credits
Icons from [Material Icons](https://developers.google.com/fonts/docs/material_icons)


## License
[MIT](LICENSE.md)