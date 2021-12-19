# course-shell-solution
Solution-课程概览与 shell
1. 在 `/tmp` 下新建一个名为 `missing` 的文件夹。
```bash
cd /tmp/
mkdir missing
ls
```
![image](https://user-images.githubusercontent.com/42760725/146666748-840119bb-a835-4388-9c76-4f090eee9235.png)  

2. 用 man 查看程序 touch 的使用手册。
```bash
man touch
```
![image](https://user-images.githubusercontent.com/42760725/146666791-57ea3ea3-c8e1-4b7f-a9b2-cfcfcd081175.png)

3. 用 touch 在 missing 文件夹中新建一个叫 semester 的文件。
```bash
cd missing
touch semester
```
![image](https://user-images.githubusercontent.com/42760725/146666897-ff09ab97-5941-4322-ab6d-e91ca742effc.png)


4. 将以下内容一行一行地写入 semester 文件：
```sh
#!/bin/sh
curl --head --silent https://missing.csail.mit.edu
```
步骤：
```bash
echo '#!/bin/sh' > semester
echo 'curl --head --silent https://missing.csail.mit.edu' >> semester
```
**注意**：`>` 和 `>>` 是不同的。  
![image](https://user-images.githubusercontent.com/42760725/146667008-8164b3fd-fc04-4ebb-81eb-98ea3190087c.png)

5. 尝试执行这个文件。
```bash
./semester
```
![image](https://user-images.githubusercontent.com/42760725/146667047-39ced53b-7d40-4580-9f35-bd5c9a1208c9.png)  
不能执行，因为没有运行权限（`x`）。

6. 查看 chmod 的手册。
```bash
man chmod
```
![image](https://user-images.githubusercontent.com/42760725/146667062-aa796bfa-f657-41f8-860f-2559ece04143.png)

7. 使用 chmod 命令改变权限，使 `./semester` 能够成功执行，不要使用 `sh semester` 来执行该程序。
```bash
chmod +x ./semester
./semester
```
![image](https://user-images.githubusercontent.com/42760725/146667107-f46bbabc-596f-42fe-ab51-3fb9a3166d4d.png)

![image](https://user-images.githubusercontent.com/42760725/146667118-f0a78118-1214-4c2d-869e-f33c79379c98.png)

8. 使用 `|` 和 `>` ，将 `semester` 文件输出的最后更改日期信息，写入主目录下的 `last-modified.txt` 的文件中
```bash
./semester | grep last-modified > ~/last-modified.txt
```
![image](https://user-images.githubusercontent.com/42760725/146667186-be4f987a-6ce0-4e74-baa9-069cf731bdaa.png)

9. 写一段命令来从 `/sys` 中获取笔记本的电量信息，或者台式机 CPU 的温度。（TODO）










