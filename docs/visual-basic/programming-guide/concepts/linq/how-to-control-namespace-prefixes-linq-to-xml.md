---
title: '방법: 컨트롤 네임 스페이스 접두사 (Visual Basic) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 2b89b49aa76df526c08143cad49685386ffd5e7c
ms.sourcegitcommit: eb9ff6f364cde6f11322e03800d8f5ce302f3c73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2019
ms.locfileid: "68709825"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="86a63-102">방법: 컨트롤 네임 스페이스 접두사 (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="86a63-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="86a63-103">이 항목에서는 네임스페이스 접두사를 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="86a63-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="86a63-104">예제</span><span class="sxs-lookup"><span data-stu-id="86a63-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="86a63-105">Description</span><span class="sxs-lookup"><span data-stu-id="86a63-105">Description</span></span>  
 <span data-ttu-id="86a63-106">이 예제에서는 두 네임스페이스를 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="86a63-106">This example declares two namespaces.</span></span> <span data-ttu-id="86a63-107">`http://www.adventure-works.com` 네임 스페이스에 `aw`접두사가 `www.fourthcoffee.com` 있고 네임 스페이스의 접두사가 `fc`임을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="86a63-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="86a63-108">코드</span><span class="sxs-lookup"><span data-stu-id="86a63-108">Code</span></span>  
  
```vb  
Imports <xmlns:aw="http://www.adventure-works.com">  
Imports <xmlns:fc="www.fourthcoffee.com">  
  
Module Module1  
  
    Sub Main()  
        Dim root As XElement = _  
            <aw:Root>  
                <fc:Child>  
                    <aw:DifferentChild>other content</aw:DifferentChild>  
                </fc:Child>  
                <aw:Child2>c2 content</aw:Child2>  
                <fc:Child3>c3 content</fc:Child3>  
            </aw:Root>  
        Console.WriteLine(root)  
    End Sub  
  
End Module  
```  
  
### <a name="comments"></a><span data-ttu-id="86a63-109">주석</span><span class="sxs-lookup"><span data-stu-id="86a63-109">Comments</span></span>  
 <span data-ttu-id="86a63-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="86a63-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="86a63-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="86a63-111">See also</span></span>

- [<span data-ttu-id="86a63-112">네임 스페이스 개요 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="86a63-112">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
