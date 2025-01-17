---
title: 如何：使用全局命名空间别名 - C# 编程指南
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- aliases [C#]
- namespaces [C#], global namespace qualifier
- global namespace [C#]
ms.assetid: 98a1d89b-3c5a-44f7-8400-c4a3c0ec22a9
ms.openlocfilehash: b163981d3cf6d56ab953757931b0b386a47263ff
ms.sourcegitcommit: bbfcc913c275885381820be28f61efcf8e83eecc
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2019
ms.locfileid: "68796292"
---
# <a name="how-to-use-the-global-namespace-alias-c-programming-guide"></a>如何：使用全局命名空间别名（C# 编程指南）
当具有同一名称的其他实体可能隐藏了成员时，访问全局[命名空间](../../../csharp/language-reference/keywords/namespace.md)中的成员的功能将十分有用。  
  
 例如，在下面的代码中，`Console` 解析为 `TestApp.Console` 而不是 <xref:System> 命名空间中的 `Console` 类型。  
  
 [!code-csharp[csProgGuide#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/using.cs#1)]  
  
 [!code-csharp[csProgGuideNamespaces#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#1)]  
  
 使用 `System.Console` 仍会导致错误，因为类 `TestApp.System` 隐藏了 `System` 命名空间：  
  
 [!code-csharp[csProgGuideNamespaces#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#2)]  
  
 但是，可以使用 `global::System.Console` 解决此错误，如下所示：  
  
 [!code-csharp[csProgGuideNamespaces#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#3)]  
  
 如果左标识符为 `global`，则会在全局命名空间开始搜索右标识符。 例如，以下声明引用 `TestApp` 作为全局空间的成员。  
  
 [!code-csharp[csProgGuideNamespaces#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideNamespaces/CS/Namespaces.cs#4)]  
  
 显然，不建议将自己的命名空间的名称创建为 `System`，并且不可能会遇到发生此情况的代码。 但是，在大型项目中，很有可能会以一种或另一种形式发生命名空间重复。 在这些情况下，全局命名空间限定符可保证指定根命名空间。  
  
## <a name="see-also"></a>请参阅

- [C# 编程指南](../../../csharp/programming-guide/index.md)
- [命名空间](../../../csharp/programming-guide/namespaces/index.md)
- [::运算符](../../../csharp/language-reference/operators/namespace-alias-qualifier.md)
- [extern](../../../csharp/language-reference/keywords/extern.md)
