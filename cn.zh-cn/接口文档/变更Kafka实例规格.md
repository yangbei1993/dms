# 变更Kafka实例规格<a name="ZH-CN_TOPIC_0140858141"></a>

## 功能介绍<a name="section11513161413553"></a>

对已购买的Kafka实例规格进行变更，可对磁盘进行扩容。

>![](public_sys-resources/icon-note.gif) **说明：**   
>-   每个实例最多可以进行20次扩容。  

## URI<a name="section26715417"></a>

POST /v1.0/\{project\_id\}/instances/\{instance\_id\}/extend

**表 1**  参数说明

<a name="table434018282110"></a>
<table><thead align="left"><tr id="row46806283114"><th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.1"><p id="p1368010288120"><a name="p1368010288120"></a><a name="p1368010288120"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.2"><p id="p86803283111"><a name="p86803283111"></a><a name="p86803283111"></a>类型</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.3"><p id="p1568018281318"><a name="p1568018281318"></a><a name="p1568018281318"></a>必选</p>
</th>
<th class="cellrowborder" valign="top" width="25%" id="mcps1.2.5.1.4"><p id="p166801828014"><a name="p166801828014"></a><a name="p166801828014"></a>备注</p>
</th>
</tr>
</thead>
<tbody><tr id="row186802285111"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p1268012813116"><a name="p1268012813116"></a><a name="p1268012813116"></a>project_id</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p86812281319"><a name="p86812281319"></a><a name="p86812281319"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p1768110283116"><a name="p1768110283116"></a><a name="p1768110283116"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p20681182818117"><a name="p20681182818117"></a><a name="p20681182818117"></a>项目ID。</p>
</td>
</tr>
<tr id="row968112281014"><td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.1 "><p id="p868112281017"><a name="p868112281017"></a><a name="p868112281017"></a>instance_id</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.2 "><p id="p9681328010"><a name="p9681328010"></a><a name="p9681328010"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.3 "><p id="p4681192819115"><a name="p4681192819115"></a><a name="p4681192819115"></a>是</p>
</td>
<td class="cellrowborder" valign="top" width="25%" headers="mcps1.2.5.1.4 "><p id="p96811287114"><a name="p96811287114"></a><a name="p96811287114"></a>实例ID。</p>
</td>
</tr>
</tbody>
</table>

## 请求消息<a name="section39112169"></a>

**请求参数**

**表 2**  参数说明

<a name="table56761820495"></a>
<table><thead align="left"><tr id="row62588155"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.5.1.1"><p id="p968314119564"><a name="p968314119564"></a><a name="p968314119564"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.2"><p id="p12683191155615"><a name="p12683191155615"></a><a name="p12683191155615"></a>是否必选</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.5.1.3"><p id="p13683181116565"><a name="p13683181116565"></a><a name="p13683181116565"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="50%" id="mcps1.2.5.1.4"><p id="p66836113568"><a name="p66836113568"></a><a name="p66836113568"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row18393353"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p11609128104815"><a name="p11609128104815"></a><a name="p11609128104815"></a>new_storage_space</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p323911448287"><a name="p323911448287"></a><a name="p323911448287"></a>否</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p032224222813"><a name="p032224222813"></a><a name="p032224222813"></a><span>Integer</span></p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p0394154512489"><a name="p0394154512489"></a><a name="p0394154512489"></a>消息存储空间，具体值根据规格的不同而定，单位为GB。</p>
<p id="p1461019282489"><a name="p1461019282489"></a><a name="p1461019282489"></a>修改的值必须大于或等于原来的值。</p>
</td>
</tr>
<tr id="row1291281516482"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.5.1.1 "><p id="p361020287489"><a name="p361020287489"></a><a name="p361020287489"></a>new_spec_code</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.2 "><p id="p823784482812"><a name="p823784482812"></a><a name="p823784482812"></a><span id="ph1394095514143"><a name="ph1394095514143"></a><a name="ph1394095514143"></a>是</span></p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.5.1.3 "><p id="p1832413429282"><a name="p1832413429282"></a><a name="p1832413429282"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="50%" headers="mcps1.2.5.1.4 "><p id="p56106287481"><a name="p56106287481"></a><a name="p56106287481"></a>填入要扩容后的新规格，<span id="ph1750124017199"><a name="ph1750124017199"></a><a name="ph1750124017199"></a>新</span>规格<span id="ph105361449191"><a name="ph105361449191"></a><a name="ph105361449191"></a>可以大于或等于原来的值</span>。</p>
<a name="ul56102028194815"></a><a name="ul56102028194815"></a><ul id="ul56102028194815"><li>dms.instance.kafka.cluster.c3.mini：Kafka实例的基准带宽为100MByte/秒。</li><li>dms.instance.kafka.cluster.c3.small：Kafka实例的基准带宽为300MByte/秒。</li><li>dms.instance.kafka.cluster.c3.middle：Kafka实例的基准带宽为600MByte/秒。</li><li>dms.instance.kafka.cluster.c3.high：Kafka实例的基准带宽为1200MByte/秒。</li></ul>
</td>
</tr>
</tbody>
</table>

>![](public_sys-resources/icon-note.gif) **说明：**   
>"new\_storage\_space"和"new\_spec\_code"参数必须二选一。  

**请求示例**

```
{
    "new_storage_space" : 4000,  
    "new_spec_code" : "dms.instance.kafka.cluster.c3.middle"
}
```

## 响应消息<a name="section111868655716"></a>

**响应参数**

**表 3**  参数说明

<a name="table079510368334"></a>
<table><thead align="left"><tr id="row53186163"><th class="cellrowborder" valign="top" width="20%" id="mcps1.2.4.1.1"><p id="p13111919"><a name="p13111919"></a><a name="p13111919"></a>参数</p>
</th>
<th class="cellrowborder" valign="top" width="15%" id="mcps1.2.4.1.2"><p id="p55432544"><a name="p55432544"></a><a name="p55432544"></a>参数类型</p>
</th>
<th class="cellrowborder" valign="top" width="65%" id="mcps1.2.4.1.3"><p id="p60851118"><a name="p60851118"></a><a name="p60851118"></a>说明</p>
</th>
</tr>
</thead>
<tbody><tr id="row29993536"><td class="cellrowborder" valign="top" width="20%" headers="mcps1.2.4.1.1 "><p id="p86571821185110"><a name="p86571821185110"></a><a name="p86571821185110"></a>job_id</p>
</td>
<td class="cellrowborder" valign="top" width="15%" headers="mcps1.2.4.1.2 "><p id="p186546213517"><a name="p186546213517"></a><a name="p186546213517"></a>String</p>
</td>
<td class="cellrowborder" valign="top" width="65%" headers="mcps1.2.4.1.3 "><p id="p12649162119511"><a name="p12649162119511"></a><a name="p12649162119511"></a>扩容任务ID。</p>
</td>
</tr>
</tbody>
</table>

**响应示例**

```
{
   "job_id"："8959ab1c-7n1a-yyb1-a05t-93dfc361b32d"
}
```

## 状态码<a name="section778761934517"></a>

操作成功的状态码如[表4](#table1467214432612)所示，其他响应见[状态码](状态码.md)。

**表 4**  状态码

<a name="table1467214432612"></a>
<table><thead align="left"><tr id="row4725344202613"><th class="cellrowborder" valign="top" width="15.15%" id="mcps1.2.3.1.1"><p id="p0725844142612"><a name="p0725844142612"></a><a name="p0725844142612"></a>状态码</p>
</th>
<th class="cellrowborder" valign="top" width="84.85000000000001%" id="mcps1.2.3.1.2"><p id="p8725134442613"><a name="p8725134442613"></a><a name="p8725134442613"></a>描述</p>
</th>
</tr>
</thead>
<tbody><tr id="row07251445263"><td class="cellrowborder" valign="top" width="15.15%" headers="mcps1.2.3.1.1 "><p id="p1257511111328"><a name="p1257511111328"></a><a name="p1257511111328"></a>200</p>
</td>
<td class="cellrowborder" valign="top" width="84.85000000000001%" headers="mcps1.2.3.1.2 "><p id="p1257510113210"><a name="p1257510113210"></a><a name="p1257510113210"></a>实例规格变更任务提交成功。</p>
</td>
</tr>
</tbody>
</table>

