---
title: 执行分组联接
description: 如何执行分组联接。
ms.date: 12/1/2016
ms.assetid: 9667daf9-a5fd-4b43-a5c4-a9c2b744000e
ms.openlocfilehash: fbdb1a69fa2f3b171935fa3a58cf9a045be0a494
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288172"
---
# <a name="perform-grouped-joins"></a>执行分组联接

分组联接对于生成分层数据结构十分有用。 它将第一个集合中的每个元素与第二个集合中的一组相关元素进行配对。  
  
 例如，一个名为 `Student` 的类或关系数据库表可能包含两个字段：`Id` 和 `Name`。 另一个名为 `Course` 的类或关系数据库表可能包含两个字段：`StudentId` 和 `CourseTitle`。 这两个数据源的分组联接（基于匹配 `Student.Id` 和 `Course.StudentId`）会对具有 `Course` 对象集合（可能为空）的每个 `Student` 进行分组。  
  
> [!NOTE]
>  第一个集合的每个元素都会出现在分组联接的结果集中（无论是否在第二个集合中找到关联元素）。 在未找到任何相关元素的情况下，该元素的相关元素序列为空。 因此，结果选择器有权访问第一个集合的每个元素。 这与非分组联接中的结果选择器不同，后者无法访问第一个集合中在第二个集合中没有匹配项的元素。  
  
 本主题中的第一个示例演示如何执行分组联接。 第二个示例演示如何使用分组联接创建 XML 元素。  
  
## <a name="example"></a>示例  
  
### <a name="group-join-example"></a>分组联接示例  
 下面的示例基于与 `Pet.Owner` 属性匹配的 `Person`，来执行类型 `Person` 和 `Pet` 的对象的分组联接。 与非分组联接（会为每个匹配生成元素对）不同，分组联接只为第一个集合的每个元素生成一个结果对象（在此示例中为 `Person` 对象）。 第二个集合中的对应元素（在此示例中为 `Pet` 对象）会分组到集合中。 最后，结果选择器函数会为每个匹配都创建一种匿名类型，其中包含 `Person.FirstName` 和 `Pet` 对象集合。  
  
 [!code-csharp[CsLINQProgJoining#5](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_1.cs)]  
  
## <a name="example"></a>示例  
  
### <a name="group-join-to-create-xml-example"></a>用于创建 XML 示例的分组联接  
 分组联接非常适合于使用 LINQ to XML 创建 XML。 下面的示例类似于上面的示例，不过结果选择器函数不会创建匿名类型，而是创建表示联接对象的 XML 元素。  
  
 [!code-csharp[CsLINQProgJoining#6](../../../samples/snippets/csharp/concepts/linq/how-to-perform-grouped-joins_2.cs)]  
 
## <a name="see-also"></a>请参阅  
 <xref:System.Linq.Enumerable.Join%2A>  
 <xref:System.Linq.Enumerable.GroupJoin%2A>  
 [执行内部联接](perform-inner-joins.md)  
 [执行左外部联接](perform-left-outer-joins.md)  
 [匿名类型](../programming-guide/classes-and-structs/anonymous-types.md)  
 
