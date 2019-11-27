---
title: '방법: 네임 스페이스 접두사 제어 (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 5ba415452a8671466c3a4c71a88731e5bd3cda60
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348383"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="b66ad-102">방법: 네임스페이스 접두사 제어(Visual Basic)(LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="b66ad-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="b66ad-103">이 항목에서는 네임스페이스 접두사를 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="b66ad-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b66ad-104">예제</span><span class="sxs-lookup"><span data-stu-id="b66ad-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="b66ad-105">설명</span><span class="sxs-lookup"><span data-stu-id="b66ad-105">Description</span></span>  
 <span data-ttu-id="b66ad-106">이 예제에서는 두 네임스페이스를 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="b66ad-106">This example declares two namespaces.</span></span> <span data-ttu-id="b66ad-107">`http://www.adventure-works.com` 네임 스페이스에 `aw`접두사가 있음을 지정 하 고 `www.fourthcoffee.com` 네임 스페이스에 `fc`접두사가 있음을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b66ad-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="b66ad-108">코드</span><span class="sxs-lookup"><span data-stu-id="b66ad-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="b66ad-109">주석</span><span class="sxs-lookup"><span data-stu-id="b66ad-109">Comments</span></span>  
 <span data-ttu-id="b66ad-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="b66ad-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="b66ad-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="b66ad-111">See also</span></span>

- [<span data-ttu-id="b66ad-112">네임 스페이스 개요 (LINQ to XML) (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b66ad-112">Namespaces Overview (LINQ to XML) (Visual Basic)</span></span>](namespaces-overview-linq-to-xml.md)
