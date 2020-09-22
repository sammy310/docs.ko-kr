---
title: <para>
ms.date: 07/20/2015
helpviewer_keywords:
- <para> XML tag
- para XML tag
ms.assetid: a3a18b6c-6416-4358-94ec-37b22675fd37
ms.openlocfilehash: 0846efbaf2afacd3d0783a2d2d8e4dae3fc8b715
ms.sourcegitcommit: d2db216e46323f73b32ae312c9e4135258e5d68e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "90872700"
---
# <a name="para-visual-basic"></a><span data-ttu-id="b8840-101">\<para>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="b8840-101">\<para> (Visual Basic)</span></span>

<span data-ttu-id="b8840-102">내용이 단락 형식으로 지정 되도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8840-102">Specifies that the content is formatted as a paragraph.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b8840-103">구문</span><span class="sxs-lookup"><span data-stu-id="b8840-103">Syntax</span></span>  
  
```xml  
<para>content</para>  
```  
  
## <a name="parameters"></a><span data-ttu-id="b8840-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="b8840-104">Parameters</span></span>  

 `content`  
 <span data-ttu-id="b8840-105">단락의 텍스트입니다.</span><span class="sxs-lookup"><span data-stu-id="b8840-105">The text of the paragraph.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="b8840-106">설명</span><span class="sxs-lookup"><span data-stu-id="b8840-106">Remarks</span></span>  

 <span data-ttu-id="b8840-107">`<para>` 태그는 [\<summary>](summary.md), [\<remarks>](remarks.md) 또는 [\<returns>](returns.md) 같은 태그 내에 사용되어 텍스트에 구조를 추가할 수 있게 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8840-107">The `<para>` tag is for use inside a tag, such as [\<summary>](summary.md), [\<remarks>](remarks.md), or [\<returns>](returns.md), and lets you add structure to the text.</span></span>  
  
 <span data-ttu-id="b8840-108">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="b8840-108">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="b8840-109">예제</span><span class="sxs-lookup"><span data-stu-id="b8840-109">Example</span></span>  

 <span data-ttu-id="b8840-110">이 예제에서는 태그를 사용 `<para>` 하 여 메서드의 설명 섹션을 `UpdateRecord` 두 단락으로 분할 합니다.</span><span class="sxs-lookup"><span data-stu-id="b8840-110">This example uses the `<para>` tag to split the remarks section for the `UpdateRecord` method into two paragraphs.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="b8840-111">참조</span><span class="sxs-lookup"><span data-stu-id="b8840-111">See also</span></span>

- [<span data-ttu-id="b8840-112">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="b8840-112">XML Comment Tags</span></span>](index.md)
