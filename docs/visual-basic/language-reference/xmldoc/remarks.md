---
title: <remarks>
ms.date: 07/20/2015
helpviewer_keywords:
- <remarks> XML tag
- remarks XML tag
ms.assetid: c6241773-a7ed-41c9-9a8b-9722a0c606a9
ms.openlocfilehash: c57ddb870192bd94301f99eb71ad29526e8efc28
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400023"
---
# <a name="remarks-visual-basic"></a><span data-ttu-id="1eac5-101">\<remarks>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="1eac5-101">\<remarks> (Visual Basic)</span></span>
<span data-ttu-id="1eac5-102">멤버의 설명 섹션을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eac5-102">Specifies a remarks section for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1eac5-103">구문</span><span class="sxs-lookup"><span data-stu-id="1eac5-103">Syntax</span></span>  
  
```xml  
<remarks>description</remarks>  
```  
  
## <a name="parameters"></a><span data-ttu-id="1eac5-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="1eac5-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="1eac5-105">멤버에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="1eac5-105">A description of the member.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="1eac5-106">설명</span><span class="sxs-lookup"><span data-stu-id="1eac5-106">Remarks</span></span>  
 <span data-ttu-id="1eac5-107">태그를 사용 `<remarks>` 하 여 형식에 대 한 정보를 추가 하 고를 사용 하 여 지정 된 정보를 보충 [\<summary>](summary.md) 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eac5-107">Use the `<remarks>` tag to add information about a type, supplementing the information specified with [\<summary>](summary.md).</span></span>  
  
 <span data-ttu-id="1eac5-108">이 정보는 개체 브라우저 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1eac5-108">This information appears in the Object Browser.</span></span> <span data-ttu-id="1eac5-109">개체 브라우저에 대 한 자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="1eac5-109">For information about the Object Browser, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="1eac5-110">[-Doc](../../reference/command-line-compiler/doc.md) 로 컴파일하여 문서 주석을 파일로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="1eac5-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="1eac5-111">예제</span><span class="sxs-lookup"><span data-stu-id="1eac5-111">Example</span></span>  
 <span data-ttu-id="1eac5-112">이 예제에서는 태그를 사용 하 여 `<remarks>` 메서드가 수행 하는 작업을 설명 합니다 `UpdateRecord` .</span><span class="sxs-lookup"><span data-stu-id="1eac5-112">This example uses the `<remarks>` tag to explain what the `UpdateRecord` method does.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="1eac5-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1eac5-113">See also</span></span>

- [<span data-ttu-id="1eac5-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="1eac5-114">XML Comment Tags</span></span>](index.md)
