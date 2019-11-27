---
title: <returns>
ms.date: 07/20/2015
helpviewer_keywords:
- returns XML tag
- <returns> XML tag
ms.assetid: a03a6469-d907-425d-882f-083187950e7e
ms.openlocfilehash: 62f70ae7f40fa3cde9492563b7bd14dfa5940a5f
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2019
ms.locfileid: "74352237"
---
# <a name="returns-visual-basic"></a><span data-ttu-id="65e79-101">\<반환 > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="65e79-101">\<returns> (Visual Basic)</span></span>
<span data-ttu-id="65e79-102">속성 또는 함수의 반환 값을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e79-102">Specifies the return value of the property or function.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="65e79-103">구문</span><span class="sxs-lookup"><span data-stu-id="65e79-103">Syntax</span></span>  
  
```xml  
<returns>description</returns>  
```  
  
## <a name="parameters"></a><span data-ttu-id="65e79-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="65e79-104">Parameters</span></span>  
 `description`  
 <span data-ttu-id="65e79-105">반환 값에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="65e79-105">A description of the return value.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="65e79-106">설명</span><span class="sxs-lookup"><span data-stu-id="65e79-106">Remarks</span></span>  
 <span data-ttu-id="65e79-107">메서드 선언의 주석에서 `<returns>` 태그를 사용 하 여 반환 값을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e79-107">Use the `<returns>` tag in the comment for a method declaration to describe the return value.</span></span>  
  
 <span data-ttu-id="65e79-108">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="65e79-108">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="65e79-109">예제</span><span class="sxs-lookup"><span data-stu-id="65e79-109">Example</span></span>  
 <span data-ttu-id="65e79-110">이 예에서는 `<returns>` 태그를 사용 하 여 `DoesRecordExist` 함수가 반환 하는 항목을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="65e79-110">This example uses the `<returns>` tag to explain what the `DoesRecordExist` function returns.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="65e79-111">참고자료</span><span class="sxs-lookup"><span data-stu-id="65e79-111">See also</span></span>

- [<span data-ttu-id="65e79-112">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="65e79-112">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
