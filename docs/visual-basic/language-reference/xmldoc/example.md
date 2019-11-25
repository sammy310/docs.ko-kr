---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 8f36ac1337dd0d1400180fbd3deae2bb24ad9c58
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74348488"
---
# <a name="example-visual-basic"></a><span data-ttu-id="5ad42-101">\<example> (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="5ad42-101">\<example> (Visual Basic)</span></span>
<span data-ttu-id="5ad42-102">Specifies an example for the member.</span><span class="sxs-lookup"><span data-stu-id="5ad42-102">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5ad42-103">구문</span><span class="sxs-lookup"><span data-stu-id="5ad42-103">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="5ad42-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5ad42-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="5ad42-105">코드 샘플에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="5ad42-105">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5ad42-106">주의</span><span class="sxs-lookup"><span data-stu-id="5ad42-106">Remarks</span></span>  
 <span data-ttu-id="5ad42-107">The `<example>` tag lets you specify an example of how to use a method or other library member.</span><span class="sxs-lookup"><span data-stu-id="5ad42-107">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="5ad42-108">여기에는 일반적으로 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 태그를 같이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="5ad42-108">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="5ad42-109">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="5ad42-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="5ad42-110">예제</span><span class="sxs-lookup"><span data-stu-id="5ad42-110">Example</span></span>  
 <span data-ttu-id="5ad42-111">This example uses the `<example>` tag to include an example for using the `ID` field.</span><span class="sxs-lookup"><span data-stu-id="5ad42-111">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="5ad42-112">참조</span><span class="sxs-lookup"><span data-stu-id="5ad42-112">See also</span></span>

- [<span data-ttu-id="5ad42-113">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="5ad42-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
