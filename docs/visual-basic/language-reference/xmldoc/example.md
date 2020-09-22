---
title: <example>
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 6e9f63e4d31df7790f51ae4d166b606f2c63f14b
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872973"
---
# <a name="example-visual-basic"></a><span data-ttu-id="9b51e-101">\<example>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="9b51e-101">\<example> (Visual Basic)</span></span>

<span data-ttu-id="9b51e-102">멤버에 대 한 예제를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="9b51e-102">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9b51e-103">구문</span><span class="sxs-lookup"><span data-stu-id="9b51e-103">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="9b51e-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9b51e-104">Parameters</span></span>  

 `description`  
 <span data-ttu-id="9b51e-105">코드 샘플에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="9b51e-105">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="9b51e-106">설명</span><span class="sxs-lookup"><span data-stu-id="9b51e-106">Remarks</span></span>  

 <span data-ttu-id="9b51e-107">`<example>` 태그를 사용하면 메서드 또는 기타 라이브러리 멤버를 사용하는 방법의 예제를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9b51e-107">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="9b51e-108">여기에는 일반적으로 [\<code>](code.md) 태그를 같이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="9b51e-108">This commonly involves using the [\<code>](code.md) tag.</span></span>  
  
 <span data-ttu-id="9b51e-109">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="9b51e-109">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="9b51e-110">예제</span><span class="sxs-lookup"><span data-stu-id="9b51e-110">Example</span></span>  

 <span data-ttu-id="9b51e-111">이 예제에서는 태그를 사용 하 여 `<example>` 필드 사용에 대 한 예제를 포함 합니다 `ID` .</span><span class="sxs-lookup"><span data-stu-id="9b51e-111">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="9b51e-112">참조</span><span class="sxs-lookup"><span data-stu-id="9b51e-112">See also</span></span>

- [<span data-ttu-id="9b51e-113">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="9b51e-113">XML Comment Tags</span></span>](index.md)
