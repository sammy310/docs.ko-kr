---
description: 다음에 대해 자세히 알아보세요. <para> (Visual Basic)
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 51dd9ff300d980b4c0576566cad5d17375889ba1
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99740771"
---
# <a name="para-visual-basic"></a><span data-ttu-id="497a1-103">\<para>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="497a1-103">\<para> (Visual Basic)</span></span>

<span data-ttu-id="497a1-104">내용이 단락 형식으로 지정 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="497a1-104">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="497a1-105">구문</span><span class="sxs-lookup"><span data-stu-id="497a1-105">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="497a1-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="497a1-106">Parameters</span></span>  

 `content`  
 <span data-ttu-id="497a1-107">단락의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="497a1-107">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="497a1-108">설명</span><span class="sxs-lookup"><span data-stu-id="497a1-108">Remarks</span></span>  

 <span data-ttu-id="497a1-109">`<para>` 태그는 [\<summary>](summary.md), [\<remarks>](remarks.md) 또는 [\<returns>](returns.md) 같은 태그 내에 사용되어 텍스트에 구조를 추가할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="497a1-109">The `<para>` tag is for use inside a tag, such as [\<summary>](summary.md), [\<remarks>](remarks.md), or [\<returns>](returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="497a1-110">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="497a1-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="497a1-111">예제</span><span class="sxs-lookup"><span data-stu-id="497a1-111">Example</span></span>  

 <span data-ttu-id="497a1-112">이 예제에서는 태그를 사용 `<para>` 하 여 메서드의 설명 섹션을 `UpdateRecord` 두 단락으로 분할 합니다.</span><span class="sxs-lookup"><span data-stu-id="497a1-112">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="497a1-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="497a1-113">See also</span></span>

- [<span data-ttu-id="497a1-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="497a1-114">XML Comment Tags</span></span>](index.md)
