---
title: '방법: LINQ to XML 예제 빌드(C#)'
ms.date: 07/20/2015
ms.assetid: e5d18fa1-2704-48fe-a44b-1564f97c9e9c
ms.openlocfilehash: 9bbd04731854d67b9276f339a15f2c7f2193f9b4
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/19/2019
ms.locfileid: "69594122"
---
# <a name="how-to-build-linq-to-xml-examples-c"></a><span data-ttu-id="cca37-102">방법: LINQ to XML 예제 빌드(C#)</span><span class="sxs-lookup"><span data-stu-id="cca37-102">How to: Build LINQ to XML Examples (C#)</span></span>
<span data-ttu-id="cca37-103">이 설명서의 다양한 코드 조각과 예제에서는 여러 가지 네임스페이스의 클래스와 형식을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="cca37-103">The various snippets and examples in this documentation use classes and types from a variety of namespaces.</span></span> <span data-ttu-id="cca37-104">C# 코드를 컴파일하는 경우 적절한 `using` 지시문을 제공해야 하고,</span><span class="sxs-lookup"><span data-stu-id="cca37-104">When compiling C# code, you need to supply appropriate `using` directives.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cca37-105">예</span><span class="sxs-lookup"><span data-stu-id="cca37-105">Example</span></span>  
 <span data-ttu-id="cca37-106">다음 코드에는 C# 예제에서 빌드하고 실행해야 하는 `using` 지시문이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cca37-106">The following code contains the `using` directives that the C# examples require to build and run.</span></span> <span data-ttu-id="cca37-107">모든 `using` 지시문이 모든 예제에 필요한 것은 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="cca37-107">Not all `using` directives are required for every example.</span></span>  
  
```csharp  
using System;  
using System.Diagnostics;  
using System.Collections;  
using System.Collections.Generic;  
using System.Collections.Specialized;  
using System.Text;  
using System.Linq;  
using System.Xml;  
using System.Xml.Linq;  
using System.Xml.Schema;  
using System.Xml.XPath;  
using System.Xml.Xsl;  
using System.IO;  
using System.Threading;  
using System.Reflection;  
using System.IO.Packaging;  
```  
  
## <a name="see-also"></a><span data-ttu-id="cca37-108">참고 항목</span><span class="sxs-lookup"><span data-stu-id="cca37-108">See also</span></span>

- [<span data-ttu-id="cca37-109">LINQ to XML 프로그래밍 개요(C#)</span><span class="sxs-lookup"><span data-stu-id="cca37-109">LINQ to XML Programming Overview (C#)</span></span>](./linq-to-xml-overview.md)
