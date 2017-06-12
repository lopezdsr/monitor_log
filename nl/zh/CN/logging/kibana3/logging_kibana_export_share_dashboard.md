---

copyright:
  years: 2016, 2017
lastupdated: "2017-02-03"

---

{:new_window: target="_blank"}
{:shortdesc: .shortdesc}
{:screen:.screen}
{:codeblock:.codeblock}


# 导出和共享 Kibana 仪表板
{: #exporting_sharing_kibana_dash}

将仪表板模式导出为 JSON 文件，或者共享日志数据的定制 Kibana 仪表板的 URL。
{:shortdesc}

使用 Kibana，可以通过将仪表板导出为 JSON 文件或者共享仪表板的 URL，实现与其他项目干系人的协作。

要将 Kibana 仪表板导出为 JSON 文件，请完成以下任务：

1. 单击**保存**图标 ![“保存”图标](images/logging_save.jpg "“保存”图标")；然后，单击**高级** **>** **导出模式**。

    ![将仪表板导出为 JSON 文件](images/logging_export_json.jpg "将仪表板导出为 JSON 文件")

2. 为 JSON 文件选择有意义的名称；然后，单击**保存**。具有此 JSON 文件的任何用户都可以在 Kibana 仪表板中打开该文件。 

要创建并共享 Kibana 仪表板的 URL，请完成以下任务：

1. 在 Kibana 仪表板上，单击**文件夹**图标 ![“文件夹”图标](images/logging_folder.jpg "“文件夹”图标") 以显示用于列出所有最近仪表板的菜单。除了按名称列出保存的仪表板外，该菜单还会根据以下格式列出未命名仪表板：*ALCH_TENANT_ID_application_id*。 

    ![仪表板列表](images/logging_list_of_dashboards.jpg "仪表板列表")

2. 对于要共享的仪表板，单击**共享**图标 ![“共享”图标](images/logging_create_url.jpg "“共享”图标")。这将创建并显示可共享的 URL。 

    ![“可共享的 URL”窗格](images/logging_shareable_link_popup.jpg "“可共享的 URL”窗格")

    复制此 URL 以便与其他用户共享仪表板。单击**关闭**以返回到仪表板。
