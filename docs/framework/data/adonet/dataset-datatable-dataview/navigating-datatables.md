---
title: 导航数据表
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 202026a1-ec79-435e-b507-12a77f5011b2
ms.openlocfilehash: 3bd10694512e828354254588361cc009aac6602f
ms.sourcegitcommit: 11f11ca6cefe555972b3a5c99729d1a7523d8f50
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/03/2018
ms.locfileid: "32756363"
---
# <a name="navigating-datatables"></a>导航数据表
<xref:System.Data.DataTableReader> 以一个或多个只读、只进结果集的形式获取一个或多个 <xref:System.Data.DataTable> 对象的内容。  
  
 如果 <xref:System.Data.DataTableReader> 是使用 <xref:System.Data.DataSet.CreateDataReader%2A> 方法创建，则可以包含多个结果集。 如果包含多个结果集，<xref:System.Data.DataTableReader.NextResult%2A> 方法会将游标前进到下一个结果集。 这是一个只进过程。 无法返回到前一个结果集。  
  
## <a name="example"></a>示例  
 在下面的示例中，`TestConstructor`方法创建两个<xref:System.Data.DataTable>实例。 为了演示此构造函数<xref:System.Data.DataTableReader>类，示例创建一个新**DataTableReader**基于包含两个数组**数据表**，并执行一个简单的操作，前几列中的内容输出到控制台窗口中。  
  
 [!code-csharp[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/CS/source.cs#1)]
 [!code-vb[DataWorks DataTableReader.NextResult#1](../../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DataWorks DataTableReader.NextResult/VB/source.vb#1)]  
  
## <a name="see-also"></a>请参阅  
 [DataTableReader](../../../../../docs/framework/data/adonet/dataset-datatable-dataview/datatablereaders.md)  
 [ADO.NET 托管提供程序和数据集开发人员中心](http://go.microsoft.com/fwlink/?LinkId=217917)
