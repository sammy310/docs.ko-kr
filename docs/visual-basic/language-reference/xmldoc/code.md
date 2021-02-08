---
description: 다음에 대해 자세히 알아보세요. <code>(Visual Basic)
title: <code>
ms.date: 07/20/2015
helpviewer_keywords:
- code XML tag
- <code> XML tag
ms.assetid: 925e5342-be05-45f2-bf66-7398bbd6710e
ms.openlocfilehash: 80fc0988f60d9d82b9c88734f86b20ebccc80b7c
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99787502"
---
# <a name="code-visual-basic"></a><span data-ttu-id="988ca-102">\<code>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="988ca-102">\<code> (Visual Basic)</span></span>

<span data-ttu-id="988ca-103">텍스트가 여러 줄의 코드 임을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="988ca-103">Indicates that the text is multiple lines of code.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="988ca-104">구문</span><span class="sxs-lookup"><span data-stu-id="988ca-104">Syntax</span></span>  
  
```xml  
<code>content</code>  
```  
  
## <a name="parameters"></a><span data-ttu-id="988ca-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="988ca-105">Parameters</span></span>  

 `content`  
 <span data-ttu-id="988ca-106">코드로 표시할 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="988ca-106">The text to mark as code.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="988ca-107">설명</span><span class="sxs-lookup"><span data-stu-id="988ca-107">Remarks</span></span>  

 <span data-ttu-id="988ca-108">태그를 사용 `<code>` 하 여 여러 줄을 코드로 표시 합니다.</span><span class="sxs-lookup"><span data-stu-id="988ca-108">Use the `<code>` tag to indicate multiple lines as code.</span></span> <span data-ttu-id="988ca-109">[\<c>](c.md)설명 내의 텍스트를 코드로 표시 해야 함을 나타내는 데 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="988ca-109">Use [\<c>](c.md) to indicate that text within a description should be marked as code.</span></span>  
  
 <span data-ttu-id="988ca-110">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="988ca-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="988ca-111">예제</span><span class="sxs-lookup"><span data-stu-id="988ca-111">Example</span></span>  

 <span data-ttu-id="988ca-112">이 예제에서는 태그를 사용 하 여 \<code> 필드를 사용 하는 예제 코드를 포함 합니다 `ID` .</span><span class="sxs-lookup"><span data-stu-id="988ca-112">This example uses the \<code> tag to include example code for using the `ID` field.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="988ca-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="988ca-113">See also</span></span>

- [<span data-ttu-id="988ca-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="988ca-114">XML Comment Tags</span></span>](index.md)
