---
title: '방법: Namespace 접두사 제어 (Visual Basic) (LINQ to XML)'
ms.date: 07/20/2015
ms.assetid: 2fcf28a5-31b6-409d-84ea-27c22f71fc9f
ms.openlocfilehash: 7e5a05d2fa93e61338f450d0a4d890fa94c04fd2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/02/2019
ms.locfileid: "58839038"
---
# <a name="how-to-control-namespace-prefixes-visual-basic-linq-to-xml"></a><span data-ttu-id="4ba3a-102">방법: Namespace 접두사 제어 (Visual Basic) (LINQ to XML)</span><span class="sxs-lookup"><span data-stu-id="4ba3a-102">How to: Control Namespace Prefixes (Visual Basic) (LINQ to XML)</span></span>
<span data-ttu-id="4ba3a-103">이 항목에서는 네임스페이스 접두사를 제어하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba3a-103">This topic describes how you can control namespace prefixes.</span></span>  
  
## <a name="example"></a><span data-ttu-id="4ba3a-104">예제</span><span class="sxs-lookup"><span data-stu-id="4ba3a-104">Example</span></span>  
  
### <a name="description"></a><span data-ttu-id="4ba3a-105">설명</span><span class="sxs-lookup"><span data-stu-id="4ba3a-105">Description</span></span>  
 <span data-ttu-id="4ba3a-106">이 예제에서는 두 네임스페이스를 선언한 다음</span><span class="sxs-lookup"><span data-stu-id="4ba3a-106">This example declares two namespaces.</span></span> <span data-ttu-id="4ba3a-107">지정 된 `http://www.adventure-works.com` 네임 스페이스가 `aw`, 하 고는 `www.fourthcoffee.com` 네임 스페이스의 접두사에 `fc`.</span><span class="sxs-lookup"><span data-stu-id="4ba3a-107">It specifies that the `http://www.adventure-works.com` namespace has the prefix `aw`, and that the `www.fourthcoffee.com` namespace has the prefix of `fc`.</span></span>  
  
### <a name="code"></a><span data-ttu-id="4ba3a-108">코드</span><span class="sxs-lookup"><span data-stu-id="4ba3a-108">Code</span></span>  
  
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
  
### <a name="comments"></a><span data-ttu-id="4ba3a-109">설명</span><span class="sxs-lookup"><span data-stu-id="4ba3a-109">Comments</span></span>  
 <span data-ttu-id="4ba3a-110">이 예제는 다음과 같은 출력을 생성합니다.</span><span class="sxs-lookup"><span data-stu-id="4ba3a-110">This example produces the following output:</span></span>  
  
```xml  
<aw:Root xmlns:fc="www.fourthcoffee.com" xmlns:aw="http://www.adventure-works.com">  
  <fc:Child>  
    <aw:DifferentChild>other content</aw:DifferentChild>  
  </fc:Child>  
  <aw:Child2>c2 content</aw:Child2>  
  <fc:Child3>c3 content</fc:Child3>  
</aw:Root>  
```  
  
## <a name="see-also"></a><span data-ttu-id="4ba3a-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="4ba3a-111">See also</span></span>

- [<span data-ttu-id="4ba3a-112">XML 네임 스페이스 (Visual Basic)를 사용 하 여 작업</span><span class="sxs-lookup"><span data-stu-id="4ba3a-112">Working with XML Namespaces (Visual Basic)</span></span>](../../../../visual-basic/programming-guide/concepts/linq/working-with-xml-namespaces.md)
