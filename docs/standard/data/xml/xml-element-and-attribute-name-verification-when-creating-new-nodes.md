---
title: 새 노드를 만들 때 XML 요소 및 특성 이름 확인
ms.date: 03/30/2017
ms.technology: dotnet-standard
ms.assetid: b489f647-a175-4659-ada4-170058bb41d0
ms.openlocfilehash: 7c99ffa9d139d94d26c562cb1668f1b855bed32d
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/07/2020
ms.locfileid: "75709948"
---
# <a name="xml-element-and-attribute-name-verification-when-creating-new-nodes"></a><span data-ttu-id="c7836-102">새 노드를 만들 때 XML 요소 및 특성 이름 확인</span><span class="sxs-lookup"><span data-stu-id="c7836-102">XML Element and Attribute Name Verification when Creating New Nodes</span></span>
<span data-ttu-id="c7836-103">XML DOM(문서 개체 모델)에서는 새 요소 노드나 특성 노드를 만들 때 해당 이름의 유효성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="c7836-103">The XML Document Object Model (DOM) checks the validity of the names when creating new element nodes or attribute nodes.</span></span> <span data-ttu-id="c7836-104">이름에 잘못된 문자가 있으면 예외가 throw됩니다.</span><span class="sxs-lookup"><span data-stu-id="c7836-104">If the names contain illegal characters, an exception is thrown.</span></span> <span data-ttu-id="c7836-105">이름이 유효하고 올바르게 인코딩되었는지 확인하려면 **XmlConvert** 클래스를 사용하여 이름을 인코딩한 다음 애플리케이션 수준에서 다시 디코딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7836-105">To ensure that names are valid and encoded correctly, you need to use the **XmlConvert** class to encode the name and decode it back at an application level.</span></span> <span data-ttu-id="c7836-106">**XmlWriter**에는 추가 작업을 수행하여 잘 구성된(Well-Formed) XML이 생성되는지 확인하는 메서드가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c7836-106">The **XmlWriter** has methods that do additional work to ensure well-formed XML is generated.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c7836-107">참조</span><span class="sxs-lookup"><span data-stu-id="c7836-107">See also</span></span>

- [<span data-ttu-id="c7836-108">XML DOM(문서 개체 모델)</span><span class="sxs-lookup"><span data-stu-id="c7836-108">XML Document Object Model (DOM)</span></span>](../../../../docs/standard/data/xml/xml-document-object-model-dom.md)
