---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 893ed299b46bd6255ca0e87d008ac53265698614
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411501"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="951f5-101">\<summary>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="951f5-101">\<summary> (Visual Basic)</span></span>
<span data-ttu-id="951f5-102">멤버의 요약을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="951f5-102">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="951f5-103">구문</span><span class="sxs-lookup"><span data-stu-id="951f5-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="951f5-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="951f5-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="951f5-105">개체에 대한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="951f5-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="951f5-106">설명</span><span class="sxs-lookup"><span data-stu-id="951f5-106">Remarks</span></span>  
 <span data-ttu-id="951f5-107">태그를 사용 `<summary>` 하 여 형식 또는 형식 멤버를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="951f5-107">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="951f5-108">[\<remarks>](remarks.md)형식 설명에 보충 정보를 추가 하려면를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="951f5-108">Use [\<remarks>](remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="951f5-109">태그에 대 한 텍스트는 `<summary>` IntelliSense의 형식에 대 한 유일한 정보 소스 이며 개체 브라우저에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="951f5-109">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="951f5-110">개체 브라우저에 대 한 자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="951f5-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="951f5-111">[-Doc](../../reference/command-line-compiler/doc.md) 로 컴파일하여 문서 주석을 파일로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="951f5-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="951f5-112">예제</span><span class="sxs-lookup"><span data-stu-id="951f5-112">Example</span></span>  
 <span data-ttu-id="951f5-113">이 예제에서는 태그를 사용 하 여 `<summary>` `ResetCounter` 메서드 및 `Counter` 속성을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="951f5-113">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="951f5-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="951f5-114">See also</span></span>

- [<span data-ttu-id="951f5-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="951f5-115">XML Comment Tags</span></span>](index.md)
