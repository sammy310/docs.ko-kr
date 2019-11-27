---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 78227a17584271f91283198e95f5aa389b3ef14b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352274"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="1e271-101">\<paramref > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1e271-101">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="1e271-102">단어를 매개 변수로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e271-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1e271-103">구문</span><span class="sxs-lookup"><span data-stu-id="1e271-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1e271-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1e271-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="1e271-105">참조할 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="1e271-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="1e271-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="1e271-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1e271-107">설명</span><span class="sxs-lookup"><span data-stu-id="1e271-107">Remarks</span></span>  
 <span data-ttu-id="1e271-108">`<paramref>` 태그는 단어가 매개 변수 임을 나타내는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e271-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="1e271-109">XML 파일을 처리 하 여이 매개 변수를 일종의 형식으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1e271-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="1e271-110">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="1e271-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1e271-111">예제</span><span class="sxs-lookup"><span data-stu-id="1e271-111">Example</span></span>  
 <span data-ttu-id="1e271-112">이 예제에서는 `<paramref>` 태그를 사용 하 여 `id` 매개 변수를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e271-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="1e271-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="1e271-113">See also</span></span>

- [<span data-ttu-id="1e271-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="1e271-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
