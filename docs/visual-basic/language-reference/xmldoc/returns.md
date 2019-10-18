---
title: <returns> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: b220c2a9aa544413c3692485f6c1eb2b64e54389
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524688"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="7949e-102">\<returns > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7949e-102">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="7949e-103">속성 또는 함수의 반환 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7949e-103">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7949e-104">구문</span><span class="sxs-lookup"><span data-stu-id="7949e-104">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="7949e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7949e-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="7949e-106">반환 값에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="7949e-106">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7949e-107">주의</span><span class="sxs-lookup"><span data-stu-id="7949e-107">Remarks</span></span>  
 <span data-ttu-id="7949e-108">메서드 선언의 주석에서 `<returns>` 태그를 사용 하 여 반환 값을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7949e-108">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="7949e-109">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="7949e-109">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7949e-110">예제</span><span class="sxs-lookup"><span data-stu-id="7949e-110">Example</span></span>  
 <span data-ttu-id="7949e-111">이 예에서는 `<returns>` 태그를 사용 하 여 `DoesRecordExist` 함수가 반환 하는 항목을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7949e-111">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="7949e-112">참조</span><span class="sxs-lookup"><span data-stu-id="7949e-112">See also</span></span>

- [<span data-ttu-id="7949e-113">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="7949e-113">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
