---
title: 使用Python爬取百度图片
description: 
date: 2024-09-30
slug: 
categories:
    - 日常
---
使用Python爬取百度图片
```py
from fake_useragent import UserAgent
import requests
import re
import uuid

headers = {"User-agent": UserAgent().random,  # 随机生成一个代理请求
           "Accept-Encoding": "gzip, deflate",
           "Accept-Language": "zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6",
           "Connection": "keep-alive",
           "cookie": 'BAIDU_WISE_UID=wapp_1726906421787_41; ZFY=cggvvWz7Y:AvYezL06fvqCimMOCYkqDMtbJ5RzE0wB1Y:C; BAIDUID_BFESS=316C0566E374307EC37BCF07E6F2F4AF:FG=1; newlogin=1; BIDUPSID=316C0566E374307EC37BCF07E6F2F4AF; BDRCVFR[dG2JNJb_ajR]=mk3SLVN4HKm; H_WISE_SIDS=60829; BDRCVFR[-pGxjrCMryR]=mk3SLVN4HKm; BDRCVFR[tox4WRQ4-Km]=mk3SLVN4HKm; BDRCVFR[A24tJn4Wkd_]=mk3SLVN4HKm; BDRCVFR[X_XKQks0S63]=mk3SLVN4HKm; firstShowTip=1; cleanHistoryStatus=0; RT="z=1&dm=baidu.com&si=a0fa21b3-7bde-440a-966a-404ccd3e6fdd&ss=m1w0jp0l&sl=i&tt=7cg&bcn=https%3A%2F%2Ffclog.baidu.com%2Flog%2Fweirwood%3Ftype%3Dperf&ld=3luz&ul=4pvi&hd=4q6a"; indexPageSugList=%5B%22cat%22%2C%22dog%22%5D; ab_sr=1.0.1_MzQwMjZkMGYwMTM5ZjAzOWYzMGZlMTU2ZjFhOWZkMjlkNDk2NjQzZTdmOTFlYmZkZDFmMjA2YjM3Y2E4YzgxYzU3MTJlYWQ0NjNiNTQwZGM4ZTJiNThmMzBlN2IzMGNmYzI3NzNhMTNhYTc2M2VmODkwZTNjMmJmYTRhNTRmNmE0YTAyNWFiY2UwZGFlM2I4YmM3MGRmM2QxYzcwYjg3Ng=='
           }

img_re = re.compile('"thumbURL":"(.*?)"')
img_format = re.compile("f=(.*).*?w")


def file_op(img):
    uuid_str = uuid.uuid4().hex
    tmp_file_name = 'E:/HQYJ/course1/images/%s.jpeg' % uuid_str
    with open(file=tmp_file_name, mode="wb") as file:
        try:
            file.write(img)
        except:
            pass


def xhr_url(url_xhr, start_num=0, page=5):
    end_num = page * 30
    for page_num in range(start_num, end_num, 30):
        resp = requests.get(url=url_xhr + str(page_num), headers=headers)
        if resp.status_code == 200:
            img_url_list = img_re.findall(resp.text)  # 这是个列表形式
            for img_url in img_url_list:
                img_rsp = requests.get(url=img_url, headers=headers)
                file_op(img=img_rsp.content)
        else:
            break
    print("内容已经全部爬取")


if __name__ == "__main__":
    org_url = "https://image.baidu.com/search/acjson?tn=resultjson_com&word={text}&pn=".format(
        text=input("输入你想检索内容:"))
    xhr_url(url_xhr=org_url, start_num=int(input("开始页:")), page=int(input("所需爬取页数:")))
```