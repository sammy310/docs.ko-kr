---
title: <summary>
ms.date: 07/20/2015
helpviewer_keywords:
- <summary> XML tag
- summary XML tag
ms.assetid: 861c847d-dd94-478a-aa23-bf4899cdc848
ms.openlocfilehash: 471d3ddb5cf5a234cb77de6d1d93309faf754359
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90865835"
---
# <a name="summary-visual-basic"></a><span data-ttu-id="3b3e0-101">\<summary>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="3b3e0-101">\<summary> (Visual Basic)</span></span>

<span data-ttu-id="3b3e0-102">멤버의 요약을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b3e0-102">Specifies the summary of the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="3b3e0-103">구문</span><span class="sxs-lookup"><span data-stu-id="3b3e0-103">Syntax</span></span>  
  
```xml  
<summary>description</summary>  
```  
  
## <a name="parameters"></a><span data-ttu-id="3b3e0-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="3b3e0-104">Parameters</span></span>  

 `description`  
 <span data-ttu-id="3b3e0-105">개체에 대한 요약입니다.</span><span class="sxs-lookup"><span data-stu-id="3b3e0-105">A summary of the object.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="3b3e0-106">설명</span><span class="sxs-lookup"><span data-stu-id="3b3e0-106">Remarks</span></span>  

 <span data-ttu-id="3b3e0-107">태그를 사용 `<summary>` 하 여 형식 또는 형식 멤버를 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b3e0-107">Use the `<summary>` tag to describe a type or a type member.</span></span> <span data-ttu-id="3b3e0-108">[\<remarks>](remarks.md)를 사용하여 형식 설명에 보충 정보를 추가할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="3b3e0-108">Use [\<remarks>](remarks.md) to add supplemental information to a type description.</span></span>  
  
 <span data-ttu-id="3b3e0-109">태그에 대 한 텍스트는 `<summary>` IntelliSense의 형식에 대 한 유일한 정보 소스 이며 개체 브라우저에도 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="3b3e0-109">The text for the `<summary>` tag is the only source of information about the type in IntelliSense, and is also displayed in the Object Browser.</span></span> <span data-ttu-id="3b3e0-110">개체 브라우저에 대 한 자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="3b3e0-110">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="3b3e0-111">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="3b3e0-111">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3b3e0-112">예제</span><span class="sxs-lookup"><span data-stu-id="3b3e0-112">Example</span></span>  

 <span data-ttu-id="3b3e0-113">이 예제에서는 태그를 사용 하 여 `<summary>` `ResetCounter` 메서드 및 `Counter` 속성을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="3b3e0-113">This example uses the `<summary>` tag to describe the `ResetCounter` method and `Counter` property.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="3b3e0-114">참조</span><span class="sxs-lookup"><span data-stu-id="3b3e0-114">See also</span></span>

- [<span data-ttu-id="3b3e0-115">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="3b3e0-115">XML Comment Tags</span></span>](index.md)
