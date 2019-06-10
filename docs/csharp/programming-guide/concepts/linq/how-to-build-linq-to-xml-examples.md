---
title: '방법: LINQ to XML 예제 빌드(C#)'
ms.date: 07/20/2015
ms.assetid: e5d18fa1-2704-48fe-a44b-1564f97c9e9c
ms.openlocfilehash: 116f708eb18d642cbe914cea1ea44bd1833f2af6
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2019
ms.locfileid: "66486069"
---
# <a name="how-to-build-linq-to-xml-examples-c"></a>방법: LINQ to XML 예제 빌드(C#)
이 설명서의 다양한 코드 조각과 예제에서는 여러 가지 네임스페이스의 클래스와 형식을 사용합니다. C# 코드를 컴파일하는 경우 적절한 `using` 지시문을 제공해야 하고,  
  
## <a name="example"></a>예제  
 다음 코드에는 C# 예제에서 빌드하고 실행해야 하는 `using` 지시문이 포함되어 있습니다. 모든 `using` 지시문이 모든 예제에 필요한 것은 아닙니다.  
  
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
  
## <a name="see-also"></a>참고 항목

- [LINQ to XML 프로그래밍 개요(C#)](../../../../csharp/programming-guide/concepts/linq/linq-to-xml-overview.md)
