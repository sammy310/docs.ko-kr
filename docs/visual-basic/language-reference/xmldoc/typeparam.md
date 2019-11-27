---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 00cb62827381146c172e0d15a2c64b167c21f025
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352183"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="71f9b-101">\<typeparam > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="71f9b-101">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="71f9b-102">형식 매개 변수 이름 및 설명을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f9b-102">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="71f9b-103">구문</span><span class="sxs-lookup"><span data-stu-id="71f9b-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="71f9b-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="71f9b-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="71f9b-105">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="71f9b-105">The name of the type parameter.</span></span> <span data-ttu-id="71f9b-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="71f9b-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="71f9b-107">형식 매개 변수에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="71f9b-107">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="71f9b-108">주의</span><span class="sxs-lookup"><span data-stu-id="71f9b-108">Remarks</span></span>  
 <span data-ttu-id="71f9b-109">제네릭 형식 또는 제네릭 멤버 선언에 대 한 주석에서 `<typeparam>` 태그를 사용 하 여 형식 매개 변수 중 하나를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f9b-109">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="71f9b-110">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="71f9b-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="71f9b-111">예제</span><span class="sxs-lookup"><span data-stu-id="71f9b-111">Example</span></span>  
 <span data-ttu-id="71f9b-112">이 예제에서는 `<typeparam>` 태그를 사용 하 여 `id` 매개 변수를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="71f9b-112">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="71f9b-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="71f9b-113">See also</span></span>

- [<span data-ttu-id="71f9b-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="71f9b-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
