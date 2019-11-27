---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 240c2131179420834e6dade729ee631c0d7811a4
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352181"
---
# <a name="value-visual-basic"></a><span data-ttu-id="b7963-101">\<값 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b7963-101">\<value> (Visual Basic)</span></span>
<span data-ttu-id="b7963-102">속성에 대 한 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7963-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b7963-103">구문</span><span class="sxs-lookup"><span data-stu-id="b7963-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b7963-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b7963-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="b7963-105">속성에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="b7963-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b7963-106">설명</span><span class="sxs-lookup"><span data-stu-id="b7963-106">Remarks</span></span>  
 <span data-ttu-id="b7963-107">`<value>` 태그를 사용 하 여 속성을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7963-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="b7963-108">Visual Studio 개발 환경에서 코드 마법사를 사용 하 여 속성을 추가 하는 경우 새 속성에 대 한 [\<요약 >](../../../visual-basic/language-reference/xmldoc/summary.md) 태그가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b7963-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](../../../visual-basic/language-reference/xmldoc/summary.md) tag for the new property.</span></span> <span data-ttu-id="b7963-109">그런 다음 속성이 나타내는 값을 설명 하는 `<value>` 태그를 수동으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7963-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="b7963-110">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b7963-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b7963-111">예제</span><span class="sxs-lookup"><span data-stu-id="b7963-111">Example</span></span>  
 <span data-ttu-id="b7963-112">이 예제에서는 `<value>` 태그를 사용 하 여 `Counter` 속성에 포함 된 값을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="b7963-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="b7963-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="b7963-113">See also</span></span>

- [<span data-ttu-id="b7963-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="b7963-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
