# Kafka实例批量删除Topic<a name="dms-api-180614003"></a>

## 功能介绍<a name="section281017251256"></a>

该接口用于向Kafka实例批量删除Topic。

该接口仅支持Kafka实例。

## URI<a name="section2989194312512"></a>

POST /v1.0/\{project\_id\}/instances/\{instance\_id\}/topics/delete

参数说明见[表1](#table999074314516)。

**表 1**  参数说明

<a name="table999074314516"></a>
<table><thead align="left"><tr id="row1611514441455"><th class="cellrowborder" valign="top" width="16%" id="mcps1.2.5.1.1"><p id="p121151744458"><a name="p121151744458"></a><a name="p121151744458"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="13%" id="mcps1.2.5.1.2"><p id="p7115114415513"><a name="p7115114415513"></a><a name="p7115114415513"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="12%" id="mcps1.2.5.1.3"><p id="p111517441957"><a name="p111517441957"></a><a name="p111517441957"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="59%" id="mcps1.2.5.1.4"><p id="p6115174418512"><a name="p6115174418512"></a><a name="p6115174418512"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row121155447517"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p15115944853"><a name="p15115944853"></a><a name="p15115944853"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="13%" headers="mcps1.2.5.1.2 "><p id="p17115244354"><a name="p17115244354"></a><a name="p17115244354"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.5.1.3 "><p id="p161154441252"><a name="p161154441252"></a><a name="p161154441252"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="59%" headers="mcps1.2.5.1.4 "><p id="p8115134420510"><a name="p8115134420510"></a><a name="p8115134420510"></a>项目ID。</p>
</td>
</tr>
<tr id="row171159441358"><td class="cellrowborder" valign="top" width="16%" headers="mcps1.2.5.1.1 "><p id="p12117204415518"><a name="p12117204415518"></a><a name="p12117204415518"></a>instance_id</p>
</td>
<td class="cellrowborder" valign="top" width="13%" headers="mcps1.2.5.1.2 "><p id="p411717442510"><a name="p411717442510"></a><a name="p411717442510"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.5.1.3 "><p id="p111784412519"><a name="p111784412519"></a><a name="p111784412519"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="59%" headers="mcps1.2.5.1.4 "><p id="p1911784411513"><a name="p1911784411513"></a><a name="p1911784411513"></a>实例ID</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section101441458"></a>

**请求参数**

参数说明见[表2](#table192144257)。

**表 2**  参数说明

<a name="table192144257"></a>
<table><thead align="left"><tr id="row141190441157"><th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.1"><p id="p11191144155"><a name="p11191144155"></a><a name="p11191144155"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.2"><p id="p61195448514"><a name="p61195448514"></a><a name="p61195448514"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="12%" id="mcps1.2.5.1.3"><p id="p11119104414518"><a name="p11119104414518"></a><a name="p11119104414518"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="53%" id="mcps1.2.5.1.4"><p id="p111915441953"><a name="p111915441953"></a><a name="p111915441953"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row1911984410515"><td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.1 "><p id="p8119154410515"><a name="p8119154410515"></a><a name="p8119154410515"></a>topics</p>
</td>
<td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.2 "><p id="p5119154417519"><a name="p5119154417519"></a><a name="p5119154417519"></a>Array</p>
</td>
<td class="cellrowborder" valign="top" width="12%" headers="mcps1.2.5.1.3 "><p id="p51191544556"><a name="p51191544556"></a><a name="p51191544556"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="53%" headers="mcps1.2.5.1.4 "><p id="p51191844655"><a name="p51191844655"></a><a name="p51191844655"></a>待删除的topic列表</p>
</td>
</tr>
</tbody>
</table>

**请求示例**

```
 {
  "topics" : ["hah", "aabb"]
 }
```

## 响应消息<a name="section19101644156"></a>

**响应参数**

参数说明见[表3](#table10111744455)。

**表 3**  参数说明

<a name="table10111744455"></a>
<table><thead align="left"><tr id="row41192441858"><th class="cellrowborder" valign="top" width="23.23%" id="mcps1.2.4.1.1"><p id="p121201944354"><a name="p121201944354"></a><a name="p121201944354"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.2"><p id="p1812011441515"><a name="p1812011441515"></a><a name="p1812011441515"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="54.55%" id="mcps1.2.4.1.3"><p id="p51207446518"><a name="p51207446518"></a><a name="p51207446518"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row15120184418519"><td class="cellrowborder" valign="top" width="23.23%" headers="mcps1.2.4.1.1 "><p id="p1112013442053"><a name="p1112013442053"></a><a name="p1112013442053"></a>topics</p>
</td>
<td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.2 "><p id="p1812019441651"><a name="p1812019441651"></a><a name="p1812019441651"></a>Array</p>
</td>
<td class="cellrowborder" valign="top" width="54.55%" headers="mcps1.2.4.1.3 "><p id="p10120244959"><a name="p10120244959"></a><a name="p10120244959"></a>Topic列表</p>
</td>
</tr>
</tbody>
</table>

**表 4**  topics参数说明

<a name="table046213306109"></a>
<table><thead align="left"><tr id="row2046612306104"><th class="cellrowborder" valign="top" width="23.23%" id="mcps1.2.4.1.1"><p id="p1646783041010"><a name="p1646783041010"></a><a name="p1646783041010"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="22.220000000000002%" id="mcps1.2.4.1.2"><p id="p9468113091015"><a name="p9468113091015"></a><a name="p9468113091015"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="54.55%" id="mcps1.2.4.1.3"><p id="p1846903011104"><a name="p1846903011104"></a><a name="p1846903011104"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row64765308104"><td class="cellrowborder" valign="top" width="23.23%" headers="mcps1.2.4.1.1 "><p id="p347823071014"><a name="p347823071014"></a><a name="p347823071014"></a>id</p>
</td>
<td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.2 "><p id="p15479730111010"><a name="p15479730111010"></a><a name="p15479730111010"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="54.55%" headers="mcps1.2.4.1.3 "><p id="p848023015100"><a name="p848023015100"></a><a name="p848023015100"></a>Topic名称</p>
</td>
</tr>
<tr id="row248183016109"><td class="cellrowborder" valign="top" width="23.23%" headers="mcps1.2.4.1.1 "><p id="p19482163018103"><a name="p19482163018103"></a><a name="p19482163018103"></a>success</p>
</td>
<td class="cellrowborder" valign="top" width="22.220000000000002%" headers="mcps1.2.4.1.2 "><p id="p3483153041011"><a name="p3483153041011"></a><a name="p3483153041011"></a>Boolean</p>
</td>
<td class="cellrowborder" valign="top" width="54.55%" headers="mcps1.2.4.1.3 "><p id="p1348413061012"><a name="p1348413061012"></a><a name="p1348413061012"></a>是否删除成功。</p>
</td>
</tr>
</tbody>
</table>

**响应示例**

```
{
  "topics" : [{
      "id" : "haha",
      "success" : true
    }, {
      "id" : "aabb",
      "success" : true
    }
  ]
}
```

## 状态码<a name="section92216442511"></a>

操作成功的状态码如[表5](#table6231844656)所示，其他响应见[状态码](状态码.md)。

**表 5**  状态码

<a name="table6231844656"></a>
<table><thead align="left"><tr id="row1512019448511"><th class="cellrowborder" valign="top" width="15.15%" id="mcps1.2.3.1.1"><p id="p1120144453"><a name="p1120144453"></a><a name="p1120144453"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="84.85000000000001%" id="mcps1.2.3.1.2"><p id="p2012019445514"><a name="p2012019445514"></a><a name="p2012019445514"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row912012447517"><td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.3.1.1 "><p id="p912044411514"><a name="p912044411514"></a><a name="p912044411514"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="84.85000000000001%" headers="mcps1.2.3.1.2 "><p id="p71201441758"><a name="p71201441758"></a><a name="p71201441758"></a>删除成功。</p>
</td>
</tr>
</tbody>
</table>

