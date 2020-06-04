---
title: <typeparam>
ms.date: 07/20/2015
helpviewer_keywords:
- typeparam XML tag
- <typeparam> XML tag
ms.assetid: 1bb5ba78-f060-478c-905c-77a2e43639af
ms.openlocfilehash: 2ad54845645172acb5b91935f5347a828510e3aa
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411488"
---
# <a name="typeparam-visual-basic"></a><span data-ttu-id="f164c-101">\<typeparam>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="f164c-101">\<typeparam> (Visual Basic)</span></span>
<span data-ttu-id="f164c-102">형식 매개 변수 이름 및 설명을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="f164c-102">Defines a type parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f164c-103">구문</span><span class="sxs-lookup"><span data-stu-id="f164c-103">Syntax</span></span>  
  
```xml  
<typeparam name="name">description</typeparam>  
```  
  
## <a name="parameters"></a><span data-ttu-id="f164c-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f164c-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="f164c-105">형식 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="f164c-105">The name of the type parameter.</span></span> <span data-ttu-id="f164c-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="f164c-106">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="f164c-107">형식 매개 변수에 대 한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="f164c-107">A description of the type parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f164c-108">설명</span><span class="sxs-lookup"><span data-stu-id="f164c-108">Remarks</span></span>  
 <span data-ttu-id="f164c-109">`<typeparam>`제네릭 형식 또는 제네릭 멤버 선언에 대 한 주석의 태그를 사용 하 여 형식 매개 변수 중 하나를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="f164c-109">Use the `<typeparam>` tag in the comment for a generic type or generic member declaration to describe one of the type parameters.</span></span>  
  
 <span data-ttu-id="f164c-110">[-Doc](../../reference/command-line-compiler/doc.md) 로 컴파일하여 문서 주석을 파일로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="f164c-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f164c-111">예제</span><span class="sxs-lookup"><span data-stu-id="f164c-111">Example</span></span>  
 <span data-ttu-id="f164c-112">이 예제에서는 태그를 사용 하 여 `<typeparam>` 매개 변수를 설명 합니다 `id` .</span><span class="sxs-lookup"><span data-stu-id="f164c-112">This example uses the `<typeparam>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#8](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#8)]  
  
## <a name="see-also"></a><span data-ttu-id="f164c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f164c-113">See also</span></span>

- [<span data-ttu-id="f164c-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="f164c-114">XML Comment Tags</span></span>](index.md)
