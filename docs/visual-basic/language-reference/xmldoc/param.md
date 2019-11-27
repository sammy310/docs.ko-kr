---
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 4405fdf2defbb27aa2146d20083fd406d1f07236
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352294"
---
# <a name="param-visual-basic"></a><span data-ttu-id="cc876-101">\<param > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="cc876-101">\<param> (Visual Basic)</span></span>
<span data-ttu-id="cc876-102">매개 변수 이름 및 설명을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc876-102">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="cc876-103">구문</span><span class="sxs-lookup"><span data-stu-id="cc876-103">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="cc876-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="cc876-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="cc876-105">메서드 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="cc876-105">The name of a method parameter.</span></span> <span data-ttu-id="cc876-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="cc876-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="cc876-107">매개 변수에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="cc876-107">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="cc876-108">설명</span><span class="sxs-lookup"><span data-stu-id="cc876-108">Remarks</span></span>  
 <span data-ttu-id="cc876-109">메서드에 대 한 매개 변수 중 하나를 설명 하기 위해 메서드 선언의 주석에서 `<param>` 태그를 사용 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc876-109">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="cc876-110">`<param>` 태그의 텍스트는 다음 위치에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cc876-110">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="cc876-111">IntelliSense의 매개 변수 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="cc876-111">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="cc876-112">자세한 내용은 [Using IntelliSense](/visualstudio/ide/using-intellisense)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc876-112">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="cc876-113">개체 브라우저.</span><span class="sxs-lookup"><span data-stu-id="cc876-113">Object Browser.</span></span> <span data-ttu-id="cc876-114">자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="cc876-114">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="cc876-115">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="cc876-115">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="cc876-116">예제</span><span class="sxs-lookup"><span data-stu-id="cc876-116">Example</span></span>  
 <span data-ttu-id="cc876-117">이 예제에서는 `<param>` 태그를 사용 하 여 `id` 매개 변수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="cc876-117">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="cc876-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="cc876-118">See also</span></span>

- [<span data-ttu-id="cc876-119">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="cc876-119">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
