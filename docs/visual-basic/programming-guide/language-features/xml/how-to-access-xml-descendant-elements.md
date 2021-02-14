---
description: '자세한 정보: 방법: XML 하위 요소 액세스 (Visual Basic)'
title: '방법: XML 하위 요소에 액세스'
ms.date: 07/20/2015
helpviewer_keywords:
- XML descendent axis property [Visual Basic]
- XML axis [Visual Basic], descendent
- descendent axis property [Visual Basic]
- XML [Visual Basic], accessing
ms.assetid: aabfa258-4112-4e7e-bab9-403f96072ef7
ms.openlocfilehash: d8f3176a91c2f637f49d2754513f3253399ee8ed
ms.sourcegitcommit: 10e719780594efc781b15295e499c66f316068b8
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/14/2021
ms.locfileid: "100433176"
---
# <a name="how-to-access-xml-descendant-elements-visual-basic"></a><span data-ttu-id="47e42-103">방법: XML 하위 요소 액세스(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="47e42-103">How to: Access XML Descendant Elements (Visual Basic)</span></span>

<span data-ttu-id="47e42-104">이 예제에서는 하위 항목 축 속성을 사용 하 여 지정 된 이름의 xml 요소에 포함 된 모든 XML 요소에 액세스 하는 방법을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="47e42-104">This example shows how to use a descendant axis property to access all XML elements that have a specified name and that are contained under an XML element.</span></span> <span data-ttu-id="47e42-105">특히, 속성을 사용 하 여 `Value` `name` 하위 항목 축 속성이 반환 하는 컬렉션의 첫 번째 요소 값을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="47e42-105">In particular, it uses the `Value` property to get the value of the first element in the collection that the `name` descendant axis property returns.</span></span> <span data-ttu-id="47e42-106">`name`하위 축 속성은 개체에 포함 된 이라는 모든 요소 `name` 를 가져옵니다 `contacts` .</span><span class="sxs-lookup"><span data-stu-id="47e42-106">The `name` descendant axis property gets all elements named `name` that are contained in the `contacts` object.</span></span> <span data-ttu-id="47e42-107">또한이 예제에서는 `phone` 하위 항목 축 속성을 사용 하 여 `phone` 개체에 포함 된 이라는 모든 하위 요소에 액세스 합니다 `contacts` .</span><span class="sxs-lookup"><span data-stu-id="47e42-107">This example also uses the `phone` descendant axis property to access all descendants named `phone` that are contained in the `contacts` object.</span></span>  
  
## <a name="example"></a><span data-ttu-id="47e42-108">예</span><span class="sxs-lookup"><span data-stu-id="47e42-108">Example</span></span>  

 [!code-vb[VbXMLSamples#31](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbXMLSamples/VB/XMLSamples13.vb#31)]  
  
## <a name="compile-the-code"></a><span data-ttu-id="47e42-109">코드 컴파일</span><span class="sxs-lookup"><span data-stu-id="47e42-109">Compile the code</span></span>  

 <span data-ttu-id="47e42-110">이 예제에는 다음 사항이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="47e42-110">This example requires:</span></span>  
  
- <span data-ttu-id="47e42-111"><xref:System.Xml.Linq> 네임스페이스에 대한 참조</span><span class="sxs-lookup"><span data-stu-id="47e42-111">A reference to the <xref:System.Xml.Linq> namespace.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="47e42-112">추가 정보</span><span class="sxs-lookup"><span data-stu-id="47e42-112">See also</span></span>

- <xref:System.Xml.Linq.XContainer.Descendants%2A?displayProperty=nameWithType>
- [<span data-ttu-id="47e42-113">XML Descendant Axis Property</span><span class="sxs-lookup"><span data-stu-id="47e42-113">XML Descendant Axis Property</span></span>](../../../language-reference/xml-axis/xml-descendant-axis-property.md)
- [<span data-ttu-id="47e42-114">XML 값 속성</span><span class="sxs-lookup"><span data-stu-id="47e42-114">XML Value Property</span></span>](../../../language-reference/xml-axis/xml-value-property.md)
- [<span data-ttu-id="47e42-115">Visual Basic에서 XML에 액세스</span><span class="sxs-lookup"><span data-stu-id="47e42-115">Accessing XML in Visual Basic</span></span>](accessing-xml.md)
- [<span data-ttu-id="47e42-116">XML</span><span class="sxs-lookup"><span data-stu-id="47e42-116">XML</span></span>](index.md)
