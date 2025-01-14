---
title: 如何：将 DataView 对象绑定到 Windows 窗体 DataGridView 控件
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 2b73d60a-6049-446a-85a7-3e5a68b183e2
ms.openlocfilehash: 1fd85fdead2e971f439841dc67d461fcf7b2e08b
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504393"
---
# <a name="how-to-bind-a-dataview-object-to-a-windows-forms-datagridview-control"></a>如何：将 DataView 对象绑定到 Windows 窗体 DataGridView 控件
<xref:System.Windows.Forms.DataGridView> 控件提供一种以表格格式显示数据的功能强大且灵活的方法。 <xref:System.Windows.Forms.DataGridView> 控件支持标准 Windows 窗体数据绑定模型，因此它可以绑定到 <xref:System.Data.DataView> 和各种其他数据源。 但在多数情况下，该控件将会绑定到用于管理数据源交互详细信息的 <xref:System.Windows.Forms.BindingSource> 组件。  
  
 有关详细信息<xref:System.Windows.Forms.DataGridView>控件，请参阅[DataGridView 控件概述](../../../../docs/framework/winforms/controls/datagridview-control-overview-windows-forms.md)。  
  
### <a name="to-connect-a-datagridview-control-to-a-dataview"></a>将 DataGridView 控件连接到 DataView  
  
1. 实现方法以处理有关从数据库检索数据的详细信息。 下面的代码示例实现 `GetData` 方法，该方法初始化 <xref:System.Data.SqlClient.SqlDataAdapter> 组件并使用该组件来填充 <xref:System.Data.DataSet>。 请确保将 `connectionString` 变量设置为适合数据库的值。 您需要访问安装有 AdventureWorks SQL Server 示例数据库的服务器。  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1getdata)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1GetData](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1getdata)]  
  
2. 在窗体的 <xref:System.Windows.Forms.Form.Load> 事件处理程序中，将 <xref:System.Windows.Forms.DataGridView> 控件绑定到 <xref:System.Windows.Forms.BindingSource> 组件并调用 `GetData` 方法，以从数据库检索数据。 <xref:System.Data.DataView>创建从 LINQ to DataSet 查询通过联系<xref:System.Data.DataTable>，然后绑定到<xref:System.Windows.Forms.BindingSource>组件。  
  
     [!code-csharp[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/csharp/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/CS/Form1.cs#ldvsample1formload)]
     [!code-vb[DP DataViewWinForms Sample#LDVSample1FormLoad](../../../../samples/snippets/visualbasic/VS_Snippets_ADO.NET/DP DataViewWinForms Sample/VB/Form1.vb#ldvsample1formload)]  
  
## <a name="see-also"></a>请参阅

- [数据绑定和 LINQ to DataSet](../../../../docs/framework/data/adonet/data-binding-and-linq-to-dataset.md)
