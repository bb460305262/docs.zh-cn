---
title: 执行自定义联接操作
description: 如何执行自定义联接操作。
ms.date: 12/1/2016
ms.assetid: 56a2a4a5-7299-497d-b3c3-23c848678911
ms.openlocfilehash: df80f4382ad5fa96fcdc41b338cbb53a3d8e6cb9
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/04/2018
ms.locfileid: "33288517"
---
# <a name="perform-custom-join-operations"></a>执行自定义联接操作

此示例演示如何执行无法使用 `join` 子句实现的联接操作。 在查询表达式中，`join` 子句只限于同等联接（并针对其进行优化），这类联接到目前为止是最常见的联接操作类型。 执行同等联接时，可能会始终使用 `join` 子句获得最佳性能。  
  
 但是，在以下情况下不能使用 `join` 子句：  
  
-   当联接依据不等式表达式时（非同等联接）。  
  
-   当联接依据多个等式或不等式表达式时。  
  
-   当必须为联接操作前的右侧（内部）序列引入临时范围变量。  
  
 若要执行不是同等联接的联接，可以使用多个 `from` 子句独立引入每个数据源。 随后可在 `where` 子句中将谓词表达式应用于每个源的范围变量。 表达式还可以采用方法调用的形式。  
  
> [!NOTE]
>  不要将这种类型的自定义联接操作与使用多个 `from` 子句访问内部集合相混淆。 有关详细信息，请参阅 [join 子句](../language-reference/keywords/join-clause.md)。  
  
## <a name="example"></a>示例  
 以下示例中的第一个方法演示一个简单的交叉联接。 必须谨慎使用交叉联接，因为它们可能会生成非常大的结果集。 但是，在创建针对其运行其他查询的源序列的某些情况下，它们可能会十分有用。  
  
 第二个方法会生成其类别 ID 在左侧类别列表中列出的所有产品的序列。 请注意，其中使用 `let` 子句和 `Contains` 方法创建临时数组。 还可以在查询前创建数组并去掉第一个 `from` 子句。  
  
 [!code-csharp[csProgGuideLINQ#64](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_1.cs)]  
  
## <a name="example"></a>示例  
 在下面的示例中，查询必须基于匹配键（对于内部（右侧）序列，无法在 join 子句本身之前获取这些键）联接两个序列。 如果使用 `join` 子句执行了此联接，则必须为每个元素调用 `Split` 方法。 使用多个 `from` 子句可使查询避免重复进行方法调用的开销。 但是，因为 `join` 经过了优化，所有在此特定情况下，它可能仍然比使用多个 `from` 子句更快。 结果的变化主要取决于方法调用的成本高低。  
  
 [!code-csharp[csProgGuideLINQ#13](../../../samples/snippets/csharp/concepts/linq/how-to-perform-custom-join-operations_2.cs)]  
  
## <a name="see-also"></a>请参阅  
 [LINQ 查询表达式](index.md)  
 [join 子句](../language-reference/keywords/join-clause.md)  
 [对 Join 子句的结果进行排序](order-the-results-of-a-join-clause.md)
