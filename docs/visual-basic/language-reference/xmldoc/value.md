---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 516ff6ba534478d066b8ca06baee46bdd4b35265
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524613"
---
# <a name="value-visual-basic"></a><span data-ttu-id="c10cc-102">\<value > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="c10cc-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="c10cc-103">속성에 대 한 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="c10cc-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c10cc-104">구문</span><span class="sxs-lookup"><span data-stu-id="c10cc-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="c10cc-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="c10cc-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="c10cc-106">속성에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="c10cc-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="c10cc-107">주의</span><span class="sxs-lookup"><span data-stu-id="c10cc-107">Remarks</span></span>  
 <span data-ttu-id="c10cc-108">@No__t_0 태그를 사용 하 여 속성을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c10cc-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="c10cc-109">Visual Studio 개발 환경에서 코드 마법사를 사용 하 여 속성을 추가 하는 경우 새 속성에 대 한 [\<summary >](../../../visual-basic/language-reference/xmldoc/summary.md) 태그를 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="c10cc-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="c10cc-110">그런 다음 속성이 나타내는 값을 설명 하는 `<value>` 태그를 수동으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="c10cc-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="c10cc-111">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="c10cc-111">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="c10cc-112">예제</span><span class="sxs-lookup"><span data-stu-id="c10cc-112">Example</span></span>  
 <span data-ttu-id="c10cc-113">이 예제에서는 `<value>` 태그를 사용 하 여 `Counter` 속성에 포함 된 값을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="c10cc-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="c10cc-114">참조</span><span class="sxs-lookup"><span data-stu-id="c10cc-114">See also</span></span>

- [<span data-ttu-id="c10cc-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="c10cc-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
