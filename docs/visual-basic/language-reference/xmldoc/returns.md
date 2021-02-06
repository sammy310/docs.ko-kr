---
description: 다음에 대해 자세히 알아보세요. <returns> (Visual Basic)
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: ba5f1e231502a67e86ffbb92cf8868c3aecb05d2
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99640383"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="02a5c-103">\<returns>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="02a5c-103">\<returns> (Visual Basic)</span></span>

<span data-ttu-id="02a5c-104">속성 또는 함수의 반환 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="02a5c-104">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="02a5c-105">구문</span><span class="sxs-lookup"><span data-stu-id="02a5c-105">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="02a5c-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="02a5c-106">Parameters</span></span>  

 `description`  
 <span data-ttu-id="02a5c-107">반환 값에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="02a5c-107">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="02a5c-108">설명</span><span class="sxs-lookup"><span data-stu-id="02a5c-108">Remarks</span></span>  

 <span data-ttu-id="02a5c-109">`<returns>`메서드의 태그를 사용 하 여 반환 값을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="02a5c-109">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="02a5c-110">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="02a5c-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="02a5c-111">예제</span><span class="sxs-lookup"><span data-stu-id="02a5c-111">Example</span></span>  

 <span data-ttu-id="02a5c-112">이 예제에서는 태그를 사용 하 여 `<returns>` 함수가 반환 하는 항목을 설명 `DoesRecordExist` 합니다.</span><span class="sxs-lookup"><span data-stu-id="02a5c-112">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="02a5c-113">참조</span><span class="sxs-lookup"><span data-stu-id="02a5c-113">See also</span></span>

- [<span data-ttu-id="02a5c-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="02a5c-114">XML Comment Tags</span></span>](index.md)
