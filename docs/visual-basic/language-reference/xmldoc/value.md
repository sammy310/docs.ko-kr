---
title: <value> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 2938d485bf6c547c792431b93fc8959c9c36befa
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61940740"
---
# <a name="value-visual-basic"></a><span data-ttu-id="14ca4-102">\<값 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="14ca4-102">\<value> (Visual Basic)</span></span>
<span data-ttu-id="14ca4-103">속성의 설명을 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="14ca4-103">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="14ca4-104">구문</span><span class="sxs-lookup"><span data-stu-id="14ca4-104">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="14ca4-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="14ca4-105">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="14ca4-106">속성에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="14ca4-106">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="14ca4-107">설명</span><span class="sxs-lookup"><span data-stu-id="14ca4-107">Remarks</span></span>  
 <span data-ttu-id="14ca4-108">사용 된 `<value>` 속성을 설명 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="14ca4-108">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="14ca4-109">Visual Studio 개발 환경에서 코드 마법사를 사용 하는 속성에 추가 하는 추가 된 [ \<요약 >](../../../visual-basic/language-reference/xmldoc/summary.md) 새 속성에 대 한 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="14ca4-109">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="14ca4-110">수동으로 추가 해야 합니다는 `<value>` 속성을 나타내는 값을 설명 하는 태그입니다.</span><span class="sxs-lookup"><span data-stu-id="14ca4-110">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="14ca4-111">[/doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="14ca4-111">Compile with [/doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="14ca4-112">예제</span><span class="sxs-lookup"><span data-stu-id="14ca4-112">Example</span></span>  
 <span data-ttu-id="14ca4-113">이 예제에서는 합니다 `<value>` 값에 대해 설명 하는 태그를 `Counter` 속성에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="14ca4-113">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="14ca4-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="14ca4-114">See also</span></span>

- [<span data-ttu-id="14ca4-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="14ca4-115">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
