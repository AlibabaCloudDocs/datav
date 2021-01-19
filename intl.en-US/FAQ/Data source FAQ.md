# Data source FAQ

This topic describes common issues that may occur when you connect DataV to a data source and provides corresponding solutions.

## What do I do if I fail to connect to my database?

You can add the IP address of your DataV server to your database whitelist or your ECS security group based on the network type and region of your database. You can also use the DataV Proxy service to connect to your database. For more information, see [Introduction to the DataV Proxy service](/intl.en-US/Advanced Skills/Introduction to the DataV Proxy service.md).

## How can I configure a CSV data source?

You can use the first row of the CSV file as the table header, and make sure that the name of each column is consistent with the field names of the required data structure from the corresponding chart.

## Which data centers can be connected to DataV over an Alibaba Cloud classic network?

The data centers in **China \(Hangzhou\)**, **China \(Shanghai\)**, and **China \(Beijing\)** are supported.

## Can I connect databases deployed on my ECS instance or other devices to DataV?

Yes, you can. However, you must open the Internet IP address of your database first. For security reasons, you can use the DataV Proxy service to connect to your database. For more information, see [Introduction to the DataV Proxy service](/intl.en-US/Advanced Skills/Introduction to the DataV Proxy service.md).

