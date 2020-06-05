---
title: <paramref>
ms.date: 07/20/2015
helpviewer_keywords:
- paramref XML tag
- <paramref> XML tag
ms.assetid: 8979d53b-beb1-41b7-b41e-6bbea1c17a03
ms.openlocfilehash: 3ca08016d3cef0c44e4f3c0bd0d017628eda606d
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84400049"
---
# <a name="paramref-visual-basic"></a><span data-ttu-id="ea966-101">\<paramref>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="ea966-101">\<paramref> (Visual Basic)</span></span>
<span data-ttu-id="ea966-102">단어를 매개 변수로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea966-102">Formats a word as a parameter.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ea966-103">구문</span><span class="sxs-lookup"><span data-stu-id="ea966-103">Syntax</span></span>  
  
```xml  
<paramref name="name"/>  
```  
  
## <a name="parameters"></a><span data-ttu-id="ea966-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ea966-104">Parameters</span></span>  
 `name`  
 <span data-ttu-id="ea966-105">참조할 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="ea966-105">The name of the parameter to refer to.</span></span> <span data-ttu-id="ea966-106">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="ea966-106">Enclose the name in double quotation marks (" ").</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="ea966-107">설명</span><span class="sxs-lookup"><span data-stu-id="ea966-107">Remarks</span></span>  
 <span data-ttu-id="ea966-108">`<paramref>`태그는 단어가 매개 변수 임을 나타내는 방법을 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea966-108">The `<paramref>` tag gives you a way to indicate that a word is a parameter.</span></span> <span data-ttu-id="ea966-109">XML 파일을 처리 하 여이 매개 변수를 일종의 형식으로 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ea966-109">The XML file can be processed to format this parameter in some distinct way.</span></span>  
  
 <span data-ttu-id="ea966-110">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="ea966-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="ea966-111">예제</span><span class="sxs-lookup"><span data-stu-id="ea966-111">Example</span></span>  
 <span data-ttu-id="ea966-112">이 예제에서는 태그를 사용 하 여 `<paramref>` `id` 매개 변수를 참조 합니다.</span><span class="sxs-lookup"><span data-stu-id="ea966-112">This example uses the `<paramref>` tag to refer to the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="ea966-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ea966-113">See also</span></span>

- [<span data-ttu-id="ea966-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="ea966-114">XML Comment Tags</span></span>](index.md)
