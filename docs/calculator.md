# 计算器

## 公差分析

### 1.工具背景概述
  尺寸链（dimensional chain）在零件加工或机器装配过程中，由互相联系的尺寸按一定顺序首尾相接排列而成的封闭尺寸组。组成尺寸链的各个尺寸称为尺寸链的环。其中，在装配或加工过程最终被间接保证精度的尺寸称为封闭环，其余尺寸称为组成环。组成环可根据其对封闭环的影响性质分为增环和减环。若其他尺寸不变，那些本身增大而封闭环也增大的尺寸称为增环，那些本身增大而封闭环减小的尺寸则称为减环。  
尺寸链是分析和技术工序尺寸的有效工具，在制订机械加工工艺过程和保证装配精度中都起着很重要的作用，利用尺寸链，可以分析确定机器零件的尺寸精度，保证加工精度和装配精度。利用该公差分析工具，结合制造商的制程能力，基于WC和RSS2种方法，计算装配尺寸链的封闭环，预测封闭环的合格率或者不良率，以此辅助设计师进行各个零件的制造公差的分配。本指南就以某尺寸链分析问题为例子，演示如何使用本工具。

### 2.操作步骤

下面通过实例说明如何使用此系统工具。为了保证轴孔装配后间隙的大小，对下图中的轴孔装配进行分析。其中D为孔的基本尺寸及公差D=50.00±0.02，d为轴的基本尺寸及公差d=49.96±0.01，x为装配后轴孔间隙。我们希望通过轴孔配合使得间隙大小x=0.05±0.02.    

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);"
    :src="$withBase('/calculator/tolerance-analysis/1.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">轴孔配合示意图</div>
</center>


**步骤一**：目标输入  
本例中目标为间隙尺寸x=0.05±0.02，所以XTarget=0.05，±T=0.02，选用3σ水平进行计算。

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/tolerance-analysis/2.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">目标输入</div>
</center>


**步骤二**：零件输入

- 本例中零件共计两个，分别是轴和孔，所以新增零件至2个。
- 设置孔的尺寸为增环其大小为50.00±0.02；设置孔的Cpk值为1.00。
- 设置轴的尺寸为减环其大小为49.96±0.01；在设置轴的Cpk值时，点击Cpk下拉菜单选取other Cpk选项，填入1.50。

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/tolerance-analysis/3.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">零件输入</div>
</center>

**步骤三**： 指标输出

由上述步骤填写的数据我们可以得知以下计算结果：
- 封闭环基本尺寸和公差：此项结果根据零件尺寸及Cpk值得到的实际配合间隙情况。
- 产品合格情况（合格率、Cpk等）：此项结果是综合目标和实际配合间隙情况得出的。

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/tolerance-analysis/4.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">指标输出</div>
</center>

**步骤四**： 图形输出

该步骤可以直观地了解配合间隙的情况。
- 产品分布图如下，绿色实线代表由配合零件得到的配合间隙实际尺寸分布情况。两条红色虚线（0.03和0.07）是配合间隙目标尺寸上下限值，在线内则为合格产品，超出则不合格。红色区域表示不合格产品的分布情况。

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/tolerance-analysis/5.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">产品分布图</div>
</center>

- 可点击区间计算，模拟计算改变目标尺寸后产品合格比例。如我们将配合间隙目标尺寸更改为0.45±0.15，则产品合格率为92.0%.

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/tolerance-analysis/6.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">区间计算</div>
</center>

## 四分法

### 1.工具背景概述

四分法是一种简单但却行之有效的决策工具，常常被用来对方案进行排序，辅助决策。使用本工具将大大缩短您的决策过程，且使得决策过程直观明朗。本指南就以旅游目的地的选取这个决策问题为例子，演示如何使用本工具。

### 2.操作步骤

**步骤一**：维度信息输入  

评价指标数量即维度数，在本例中，我们从【旅行经济性、自然风景、历史人文风景】三个指标对目的地进行评估。  
选择维数度为3之后在维度1、2、3文字框中键入指标名称【旅行经济性、自然风景、历史人文风景】。

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/quartered-method/1.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">维度信息输入</div>
</center>

**步骤二**：维度表格填写

不同指标的重要度可能会有所不同，在这个步骤我们希望通过对两两指标的比较实现对全部指标重要程度的排序。在本例中，有三个指标【旅行经济性、自然风景、历史人文风景】，我们希望对这三个指标进行重要度排序。在填写维度时，以行为基准，列为比较项，只需填写矩阵的右上角绿色的部分。在量化时，认为行重要度远超列，则填4；若行稍微超过列，则填3；若行列相当，则填2；若行弱于列，则填1；若行远弱于列，则填0。  
如本例中，第一行以指标为旅行经济性为基准，数字1代表旅行经济性重要程度不如自然风景，数字2代表旅行经济性和历史人文风景差不多。第二行以自然风景为基准，数字4代表自然风景重要程度远超历史人文风景。  
填写之后系统会自动生成各个指标权重，本例子中权重：旅行经济性=0.28、自然风景=0.50、历史人文风景=0.22，数字越大表明重要度越大。  

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/quartered-method/2.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">维度表格填写</div>
</center>


**步骤三**： 方案信息输入

在该步骤我们需要输入待评价方案的数目和名称。在本例中，旅游目的地方案有两个【北京、九寨沟】。  
选择方案数为2之后在文字框中键入方案称，方案一：北京、方案二：九寨沟。  

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/quartered-method/3.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">方案信息输入</div>
</center>

**步骤四**：方案评估

在该步骤我们需要输入待评价方案在各个指标的表现情况。在本例中，旅行经济型方面北京表现为好，九寨沟为不好；自然风景方面北京表现为不好，九寨沟为好；历史人文风景方面北京表现为好，九寨沟为一般。  

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/quartered-method/4.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">方案评估</div>
</center>

**步骤五**：方案评估结果

再填写完以上步骤之后便可查看方案评估结果。由柱状图可知，九寨沟的表现要优于北京  

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/quartered-method/5.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">方案评估结果</div>
</center>

## Cp推算缺陷率
 
下面通过实例说明如何使用此系统工具。现需加工一批轴类零件，图纸中轴的基本尺寸及公差D=50.00±0.02，已知当前加工工序的Cp=1.33。求加工完成后，尺寸在49.99~50.03之间零件的比率和分布情况。    

**步骤一**：信息输入  
输入基本尺寸M=50，尺寸上限USL=50.02，尺寸下限LSL=49.98，Cp=1.33，计算区间[49.99,50.03]

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/cp-probability/1.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">信息输入</div>
</center>

**步骤二**： 计算结果

计算结果显示区间概率为97.7%，表明有97.7%的产品尺寸分布在49.99~50.03内。产品分布图如下，绿色实线代表加工出的零件实际尺寸分布情况，两条蓝色虚线是计算曲线临界值，蓝色区域表示在计算区间内产品的分布情况。

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/cp-probability/2.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">计算结果</div>
</center>

## 卡扣计算
 
下面通过实例说明如何使用此系统工具。现需设计一款卡扣，具体参数参照卡口示意图如下。    
材质|悬臂类型|悬臂长度L(mm)|悬臂宽度b(mm)|许用过盈量Y(mm)|导入角度α/导出角度β|配对情况
:--:|:--:|:--:|:--:|:--:|:--:|:--:
ABS|变截面|6|2|2|20|ABS-钢

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/buckle-calculation/1.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">卡口示意图</div>
</center>

**步骤一**：材质信息查询  

在参考图例中查询材料属性
正割模数Es(MPa)|许用应变εmp(%)|摩擦系数μ
:--:|:--:|:--:|
1800|3|0.5

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/buckle-calculation/2.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">材质参考图例</div>
</center>

**步骤二**：输入  
输入卡口基本信息
悬臂类型|悬臂长度L(mm)|悬臂宽度b(mm)|许用过盈量Y(mm)|导入角度α/导出角度β|正割模数Es(MPa)|许用应变εmp(%)|摩擦系数μ
:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|:--:|
变截面|6|2|2|20|1800|3|0.5

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/buckle-calculation/3.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">卡口信息输入</div>
</center>

**步骤三**： 输出

计算结果显示
悬臂根部厚度h(mm)|挠曲力P(N)|卡入力W1(N)/保持力W2(N)
:--:|:--:|:--:|
0.589|1.039|0.704

<center>
    <img style="border-radius: 0.3125em;
    box-shadow: 0 2px 4px 0 rgba(34,36,38,.12),0 2px 10px 0 rgba(34,36,38,.08);" 
    :src="$withBase('/calculator/buckle-calculation/4.PNG')">
    <br>
    <div style="color:orange; border-bottom: 1px solid #d9d9d9;
    display: inline-block;
    color: #999;
    padding: 2px;">计算结果</div>
</center>
