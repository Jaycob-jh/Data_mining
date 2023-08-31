#!/usr/bin/env python
# -*- coding: utf-8 -*-
# @Time : 2023/8/31 15:36
# @Author : jh_jiahai@163.com

import os
import pandas as pd

folder_path = '/Users/cuilab/Desktop/App_behaviour/data'
file_list = os.listdir(folder_path)

for file_name in file_list:
    if file_name.endswith(".xlsx"):
        file_path = os.path.join(folder_path, file_name)

        xls = pd.ExcelFile(file_path)
        print(f"文件: {file_name}")
        for sheet_name in xls.sheet_names:
            df = pd.read_excel(file_path, sheet_name=sheet_name)
            df["得分"] = df.apply(lambda row: 1 if row["正式阶段正确答案"] == row["正式阶段被试按键"] else 0, axis = 1)
            correct_rate = df["得分"].mean()

            print(f"工作表: {sheet_name}, 正确率: {correct_rate}")


