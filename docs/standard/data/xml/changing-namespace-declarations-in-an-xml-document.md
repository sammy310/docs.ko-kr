---
title: XML 문서에서 네임스페이스 선언 변경
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
ms.assetid: a2758f40-e497-4964-8d8d-1bb68af14dcd
ms.openlocfilehash: e55486feeb427c95a9394ac83758e6052603921e
ms.sourcegitcommit: 33deec3e814238fb18a49b2a7e89278e27888291
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "84291580"
---
# <a name="changing-namespace-declarations-in-an-xml-document"></a><span data-ttu-id="2c9ad-102">XML 문서에서 네임스페이스 선언 변경</span><span class="sxs-lookup"><span data-stu-id="2c9ad-102">Changing Namespace Declarations in an XML Document</span></span>
<span data-ttu-id="2c9ad-103">**XmlDocument**는 네임스페이스 선언 및 **xmlns** 특성을 문서 개체 모델의 일부로 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ad-103">The **XmlDocument** exposes namespace declarations and **xmlns** attributes as part of the document object model.</span></span> <span data-ttu-id="2c9ad-104">이러한 특성은 **XmlDocument**에 저장되므로 문서를 저장할 때 해당 특성의 위치를 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ad-104">These are stored in the **XmlDocument**, so when you save the document, it can preserve the location of those attributes.</span></span> <span data-ttu-id="2c9ad-105">이러한 특성을 변경해도 트리에 있는 다른 노드의 **Name**, **NamespaceURI** 및 **Prefix** 속성에는 영향을 주지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ad-105">Changing these attributes has no affect on the **Name**, **NamespaceURI**, and **Prefix** properties of other nodes already in the tree.</span></span> <span data-ttu-id="2c9ad-106">예를 들어, 다음 문서를 로드하면 `test` 요소에 **NamespaceURI** `123.`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ad-106">For example, if you load the following document, then the `test` element has **NamespaceURI** `123.`</span></span>  
  
```xml  
<test xmlns="123"/>  
```  
  
 <span data-ttu-id="2c9ad-107">다음과 같이 `xmlns` 특성을 제거해도 `test` 요소의 **NamespaceURI**는 여전히 `123`입니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ad-107">If you remove the `xmlns` attribute as follows, then the `test` element still has the **NamespaceURI** of `123`.</span></span>  
  
```vb  
doc.documentElement.RemoveAttribute("xmlns")  
```  
  
```csharp  
doc.documentElement.RemoveAttribute("xmlns");  
```  
  
 <span data-ttu-id="2c9ad-108">마찬가지로 다음과 같이 `doc` 요소에 다른 `xmlns` 특성을 추가하면 `test` 요소에는 여전히 **NamespaceURI** `123`가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ad-108">Likewise, if you add a different `xmlns` attribute to the `doc` element as follows, then the `test` element still has **NamespaceURI** `123`.</span></span>  
  
```vb  
doc.documentElement.SetAttribute("xmlns","456")
```  
  
```csharp  
doc.documentElement.SetAttribute("xmlns","456");  
```  
  
 <span data-ttu-id="2c9ad-109">따라서 `xmlns` 특성을 변경해도 **XmlDocument** 개체를 저장하고 다시 로드하지 않는 한 아무 영향도 미치지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="2c9ad-109">Therefore, changing `xmlns` attributes will have no affect until you save and reload the **XmlDocument** object.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2c9ad-110">참조</span><span class="sxs-lookup"><span data-stu-id="2c9ad-110">See also</span></span>

- [<span data-ttu-id="2c9ad-111">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="2c9ad-111">XML Document Object Model (DOM)</span></span>](xml-document-object-model-dom.md)
