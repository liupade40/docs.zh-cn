---
title: LINQ to SQL
ms.date: 03/30/2017
ms.assetid: 73d13345-eece-471a-af40-4cc7a2f11655
ms.openlocfilehash: 257db62fcdaba454f528c2eecedfef735291f4af
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33355228"
---
# <a name="linq-to-sql"></a>LINQ to SQL
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 是 [!INCLUDE[dnprdnshort](../../../../../../includes/dnprdnshort-md.md)] 3.5 版的一个组件，提供了用于将关系数据作为对象管理的运行时基础结构。  
  
> [!NOTE]
>  关系数据显示为由二维表（关系或平面文件）组成的集合，其中公共列将表互相关联起来。 若要有效地使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]，您必须略为熟悉关系数据库的基本原理。  
  
 在 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 中，关系数据库的数据模型映射到用开发人员所用的编程语言表示的对象模型。 当应用程序运行时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会将对象模型中的语言集成查询转换为 SQL，然后将它们发送到数据库进行执行。 当数据库返回结果时，[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 会将它们转换回您可以用您自己的编程语言处理的对象。  
  
 通常使用 Visual Studio 的开发人员使用[!INCLUDE[vs_ordesigner_long](../../../../../../includes/vs-ordesigner-long-md.md)]，它提供用于实现许多功能的用户界面[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]。  
  
 此版本的 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 附带的文档介绍了生成 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 应用程序所需的基本构造块、流程和技术。 你还可以搜索 Microsoft 文档的特定问题，并且可以参与[LINQ 论坛](http://go.microsoft.com/fwlink/?LinkId=76488)，可以与专家们讨论更复杂的主题的详细信息。 最后， [LINQ to SQL： 关系数据的.net 语言集成查询](http://go.microsoft.com/fwlink/?LinkId=93205)白皮书详细介绍[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)]技术，并包含 Visual Basic 和 C# 代码示例。  
  
## <a name="in-this-section"></a>本节内容  
 [入门](../../../../../../docs/framework/data/adonet/sql/linq/getting-started.md)  
 提供对 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的简要概述以及有关如何开始使用 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的信息。  
  
 [编程指南](../../../../../../docs/framework/data/adonet/sql/linq/programming-guide.md)  
 提供映射、查询、更新、调试及类似任务的步骤。  
  
 [参考](../../../../../../docs/framework/data/adonet/sql/linq/reference.md)  
 提供有关 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的多个方面的参考信息。 相关主题包括“SQL-CLR 类型映射”、“标准查询运算符转换”等。  
  
 [示例](../../../../../../docs/framework/data/adonet/sql/linq/samples.md)  
 提供指向 Visual Basic 和 C# 示例。  
  
## <a name="related-sections"></a>相关章节  
 [LINQ（语言集成查询）](http://msdn.microsoft.com/library/a73c4aec-5d15-4e98-b962-1274021ea93d)  
 提供对 [!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)] 技术的概述。  
  
 [LINQ](../../../../../visual-basic/programming-guide/language-features/linq/index.md)  
 描述[!INCLUDE[vbteclinq](../../../../../../includes/vbteclinq-md.md)]为 Visual Basic 用户的技术。  
  
 [LINQ to ADO.NET](http://msdn.microsoft.com/library/be3297b9-1b54-4d4c-82a8-add0d79c2006)  
 链接到 [!INCLUDE[vstecado](../../../../../../includes/vstecado-md.md)] 门户。  
  
 [LINQ to SQL 演练](http://msdn.microsoft.com/library/308e66ac-f704-4e00-9b4e-7af0045a2374)  
 列出可用于 [!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] 的演练。  
  
 [下载示例数据库](../../../../../../docs/framework/data/adonet/sql/linq/downloading-sample-databases.md)  
 介绍如何下载文档中使用的示例数据库。  
  
 [LinqDataSource 技术概述](http://msdn.microsoft.com/library/104cfc3f-7385-47d3-8a51-830dfa791136)  
 介绍 <xref:System.Web.UI.WebControls.LinqDataSource> 控件如何通过 [!INCLUDE[vbteclinqext](../../../../../../includes/vbteclinqext-md.md)] 数据源控件结构向 Web 开发人员公开 [!INCLUDE[vstecasp](../../../../../../includes/vstecasp-md.md)]。
