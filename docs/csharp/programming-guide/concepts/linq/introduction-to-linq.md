---
title: LINQ 简介 (C#)
ms.date: 07/20/2015
ms.assetid: 54874feb-55e5-4ca8-a9d6-1c1127fd7fb1
ms.openlocfilehash: 3c32c20efec55568a668c5dba55baf8f3ebbee7a
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33323311"
---
# <a name="introduction-to-linq-c"></a>LINQ 简介 (C#)
语言集成查询 (LINQ) 是 .NET Framework 3.5 版中引入的一项创新功能，它在对象领域和数据领域之间架起了一座桥梁。  
  
 传统上，针对数据的查询都以简单的字符串表示，而没有编译时类型检查或 IntelliSense 支持。 此外，还需要针对每种数据源学习一种不同的查询语言：SQL 数据库、XML 文档、各种 Web 服务等等。 LINQ 使查询成为 C# 中的一流语言构造。 可以使用语言关键字和熟悉的运算符针对强类型化对象集合编写查询。  
  
 在 C# 中可为以下对象编写 LINQ 查询：SQL Server 数据库、XML 文档、ADO.NET 数据集以及支持 <xref:System.Collections.IEnumerable> 或泛型 <xref:System.Collections.Generic.IEnumerable%601> 接口的任何对象集合。 此外，第三方也为许多 Web 服务和其他数据库实现提供了 LINQ 支持。  
  
 LINQ 查询既可在新项目中使用，也可在现有项目中与非 LINQ 查询一起使用。 唯一的要求是项目应面向 .NET Framework 3.5 或更高版本。  
  
 下图为 Visual Studio 中的图例，显示了使用 C# 和 Visual Basic 针对 SQL Server 数据库编写的不完整 LINQ 查询，并具有完全类型检查和 IntelliSense 支持。  
  
 ![具有 Intellisense 的 LINQ 查询](../../../../csharp/programming-guide/concepts/linq/media/query_intell.png "Query_Intell")  
  
## <a name="next-steps"></a>后续步骤  
 若要了解有关 LINQ 的详细信息，请先熟悉入门部分 [C# 中的 LINQ 入门](../../../../csharp/programming-guide/concepts/linq/getting-started-with-linq.md)中的一些基本概念，然后阅读你感兴趣的 LINQ 技术的文档：  
  
-   SQL Server 数据库：[LINQ to SQL](../../../../../docs/framework/data/adonet/sql/linq/index.md)  
  
-   XML 文档：[LINQ to XML (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml.md)  
  
-   ADO.NET 数据集：[LINQ to DataSet](../../../../framework/data/adonet/linq-to-dataset.md)  
  
-   .NET 集合、文件、字符串等：[LINQ to Objects (C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-objects.md)  
  
## <a name="see-also"></a>请参阅  
 [语言集成查询 (LINQ) (C#)](../../../../csharp/programming-guide/concepts/linq/index.md)
