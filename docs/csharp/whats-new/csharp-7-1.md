---
title: C# 7.1 中的新增功能
description: C# 7.1 中的新增功能概述。
ms.date: 08/16/2017
ms.openlocfilehash: 565db102284424f9d8f6fa04ec9c74b52c9da0e6
ms.sourcegitcommit: bbf70abe6b46073148f78cbf0619de6092b5800c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/04/2018
ms.locfileid: "34728649"
---
# <a name="whats-new-in-c-71"></a>C# 7.1 中的新增功能

C# 7.1 是 C# 语言的第一个点版本（更新版本）。 它标志着该语言发布节奏的加速。 理想情况下，可以在每个新功能准备就绪时更快推出新功能。 C# 7.1 增加了将编译器配置为匹配特定语言版本的功能。 从而可以分别制定有关升级语言版本的决策和有关升级工具的决策。

C# 7.1 增加了[语言版本选择](../language-reference/configure-language-version.md)配置元素、三个新的语言功能和新的编译器行为。

此版本中新增的语言功能包括：

* [`async` `Main` 方法](#async-main)
  - 应用程序的入口点可以含有 `async` 修饰符。
* [`default` 文本表达式](#default-literal-expressions)
  - 在可以推断目标类型的情况下，可在默认值表达式中使用默认文本表达式。
* [推断元组元素名称](#inferred-tuple-element-names)
  - 在许多情况下，可通过元组初始化来推断元组元素的名称。

最后，编译器有 `/refout` 和 `/refonly` 两个选项，可用于控制[引用程序集生成](#reference-assembly-generation)。

若要使用单点版本中的最新功能，需要[配置编译器语言版本](../language-reference/configure-language-version.md)并选择该版本。

## <a name="async-main"></a>异步 `main` 方法


*异步 Main* 方法使你能够在 `Main` 方法中使用 `await` 关键字。
在过去，需要编写：

```csharp
static int Main()
{
    return DoAsyncWork().GetAwaiter().GetResult();
}
```

现在，您可以编写：

```csharp
static async Task<int> Main()
{
    // This could also be replaced with the body
    // DoAsyncWork, including its await expressions:
    return await DoAsyncWork();
}
```

如果程序不返回退出代码，可以声明返回 <xref:System.Threading.Tasks.Task> 的 `Main` 方法:


```csharp
static async Task Main()
{
    await SomeAsyncMethod();
}
```

你可以在编程指南的[异步 Main 方法](../programming-guide/main-and-command-args/index.md)主题中阅读更多详细信息。

## <a name="default-literal-expressions"></a>默认文本表达式

默认文本表达式是针对默认值表达式的一项增强功能。
这些表达式将变量初始化为默认值。 过去会这么编写：

```csharp
Func<string, bool> whereClause = default(Func<string, bool>);
```

现在，可以省略掉初始化右侧的类型：

```csharp
Func<string, bool> whereClause = default;
```

你可以通过 C# 编程指南的[默认值表达式](../programming-guide/statements-expressions-operators/default-value-expressions.md) 主题了解有关此增强功能的详细信息。


此增强功能也会更改某些[default 关键字](../language-reference/keywords/default.md) 的分析规则。

## <a name="inferred-tuple-element-names"></a>推断元组元素名称

此功能是对 C# 7.0 中引入的元组功能一次小型增强。 在初始化元组时，许多时候，赋值操作右侧的变量名与用于元组元素的名称相同：

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count: count, label: label);
```

元组元素的名称可通过在 C# 7.1 中初始化元组时使用的变量进行推断：

```csharp
int count = 5;
string label = "Colors used in the map";
var pair = (count, label); // element names are "count" and "label"
```

可以在[元组](../tuples.md)主题中了解有关此功能的详细信息。

## <a name="reference-assembly-generation"></a>引用程序集生成

有两个新的编译器选项会生成“仅引用”程序集：[/refout](../language-reference/compiler-options/refout-compiler-option.md) 和 [/refonly](../language-reference/compiler-options/refonly-compiler-option.md)。
链接的主题详细介绍了这些选项和引用程序集。
