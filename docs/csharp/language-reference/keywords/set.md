---
title: set（C# 参考）
ms.date: 03/10/2017
f1_keywords:
- set
- set_CSharpKeyword
helpviewer_keywords:
- set keyword [C#]
ms.assetid: 30d7e4e5-cc2e-4635-a597-14a724879619
ms.openlocfilehash: 5baab41a0f9fc81bbf9f606ef569f0653b873e26
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33265783"
---
# <a name="set-c-reference"></a>set（C# 参考）
`set` 关键字在属性或索引器中定义访问器，它会向属性或索引器元素分配值。 有关详细信息和示例，请参阅[属性](../../../csharp/programming-guide/classes-and-structs/properties.md)、[自动实现的属性](../../../csharp/programming-guide/classes-and-structs/auto-implemented-properties.md)和[索引器](../../../csharp/programming-guide/indexers/index.md)。  
  
下面的示例为名为 `Seconds` 的属性同时定义 `get` 和 `set` 访问器。 它使用名为 `_seconds` 的私有字段备份属性值。  
 
 [!code-csharp[set#1](../../../../samples/snippets/csharp/language-reference/keywords/get/get-1.cs)]  

通常，`set` 访问器包含返回一个值的单个语句，如前面的示例所示。 从 C# 7.0 开始，可以将 `set` 访问器作为 expression-bodied 成员实现。 下面的示例将 `get` 和 `set` 访问器都作为表达式主体成员实现。

 [!code-csharp[set#3](../../../../samples/snippets/csharp/language-reference/keywords/get/get-3.cs)]   
    
对于属性的 `get` 和 `set` 访问器不执行除设置或检索私有支持字段中的值以外的任何其他操作的简单情况，可以利用 C# 编译器对自动实现的属性的支持。 以下示例将 `Hours` 作为自动实现的属性来实现。 
  
 [!code-csharp[set#2](../../../../samples/snippets/csharp/language-reference/keywords/get/get-2.cs)]  
    
## <a name="c-language-specification"></a>C# 语言规范  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>请参阅  
 [C# 参考](../../../csharp/language-reference/index.md)  
 [C# 编程指南](../../../csharp/programming-guide/index.md)  
 [C# 关键字](../../../csharp/language-reference/keywords/index.md)  
 [属性](../../../csharp/programming-guide/classes-and-structs/properties.md)
