---
description: 다음에 대해 자세히 알아보세요. <summary> (Visual Basic)
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 4d4b1ecf0fa054eb625c1a3cf09c1cab4e661ef2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640292"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="2467e-103">\<summary>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2467e-103">\<summary> (Visual Basic)</span></span>

<span data-ttu-id="2467e-104">멤버의 요약을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="2467e-104">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2467e-105">구문</span><span class="sxs-lookup"><span data-stu-id="2467e-105">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2467e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2467e-106">Parameters</span></span>  

 `description`  
 <span data-ttu-id="2467e-107">개체에 대한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="2467e-107">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2467e-108">설명</span><span class="sxs-lookup"><span data-stu-id="2467e-108">Remarks</span></span>  

 <span data-ttu-id="2467e-109">태그를 사용 `<summary>` 하 여 형식 또는 형식 멤버를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2467e-109">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="2467e-110">[\<remarks>](remarks.md)를 사용하여 형식 설명에 보충 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2467e-110">Use [\<remarks>](remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="2467e-111">태그에 대 한 텍스트는 `<summary>` IntelliSense의 형식에 대 한 유일한 정보 소스 이며 개체 브라우저에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2467e-111">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="2467e-112">개체 브라우저에 대 한 자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2467e-112">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="2467e-113">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2467e-113">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2467e-114">예제</span><span class="sxs-lookup"><span data-stu-id="2467e-114">Example</span></span>  

 <span data-ttu-id="2467e-115">이 예제에서는 태그를 사용 하 여 `<summary>` `ResetCounter` 메서드 및 `Counter` 속성을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="2467e-115">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="2467e-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2467e-116">See also</span></span>

- [<span data-ttu-id="2467e-117">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="2467e-117">XML Comment Tags</span></span>](index.md)
