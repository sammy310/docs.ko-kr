---
title: <example> (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- example XML tag
- <example> XML tag
ms.assetid: 90eeda1c-3fc4-427c-879c-5046d265a97c
ms.openlocfilehash: 8f28dbf19bc03cb9d91323e9fa43a7081c1990db
ms.sourcegitcommit: 4f4a32a5c16a75724920fa9627c59985c41e173c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/17/2019
ms.locfileid: "72524011"
---
# <a name="example-visual-basic"></a><span data-ttu-id="d9019-102">\<example > (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="d9019-102">\<example> (Visual Basic)</span></span>
<span data-ttu-id="d9019-103">멤버에 대 한 예제를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9019-103">Specifies an example for the member.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d9019-104">구문</span><span class="sxs-lookup"><span data-stu-id="d9019-104">Syntax</span></span>  
  
```xml  
<example>description</example>  
```  
  
## <a name="parameters"></a><span data-ttu-id="d9019-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d9019-105">Parameters</span></span>  
 `description`  
 <span data-ttu-id="d9019-106">코드 샘플에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="d9019-106">A description of the code sample.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d9019-107">주의</span><span class="sxs-lookup"><span data-stu-id="d9019-107">Remarks</span></span>  
 <span data-ttu-id="d9019-108">@No__t_0 태그를 사용 하 여 메서드 또는 다른 라이브러리 멤버를 사용 하는 방법에 대 한 예제를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d9019-108">The `<example>` tag lets you specify an example of how to use a method or other library member.</span></span> <span data-ttu-id="d9019-109">여기에는 일반적으로 [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) 태그를 같이 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="d9019-109">This commonly involves using the [\<code>](../../../visual-basic/language-reference/xmldoc/code.md) tag.</span></span>  
  
 <span data-ttu-id="d9019-110">[-doc](../../../visual-basic/reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="d9019-110">Compile with [-doc](../../../visual-basic/reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9019-111">예제</span><span class="sxs-lookup"><span data-stu-id="d9019-111">Example</span></span>  
 <span data-ttu-id="d9019-112">이 예에서는 `<example>` 태그를 사용 하 여 `ID` 필드를 사용 하는 예제를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="d9019-112">This example uses the `<example>` tag to include an example for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="d9019-113">참조</span><span class="sxs-lookup"><span data-stu-id="d9019-113">See also</span></span>

- [<span data-ttu-id="d9019-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="d9019-114">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
