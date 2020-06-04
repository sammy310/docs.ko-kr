---
title: <value>
ms.date: 07/20/2015
helpviewer_keywords:
- <value> XML tag
- value XML tag
ms.assetid: 0b84b02e-9e6d-41b5-a926-0d5dc76dacb5
ms.openlocfilehash: 24358a1b004f1cefbfeb3fb8451380ed883841df
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2020
ms.locfileid: "84411475"
---
# <a name="value-visual-basic"></a><span data-ttu-id="7091a-101">\<value>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7091a-101">\<value> (Visual Basic)</span></span>
<span data-ttu-id="7091a-102">속성에 대 한 설명을 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="7091a-102">Specifies the description of a property.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7091a-103">구문</span><span class="sxs-lookup"><span data-stu-id="7091a-103">Syntax</span></span>  
  
```xml  
<value>property-description</value>  
```  
  
## <a name="parameters"></a><span data-ttu-id="7091a-104">매개 변수</span><span class="sxs-lookup"><span data-stu-id="7091a-104">Parameters</span></span>  
 `property-description`  
 <span data-ttu-id="7091a-105">속성에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="7091a-105">A description for the property.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="7091a-106">설명</span><span class="sxs-lookup"><span data-stu-id="7091a-106">Remarks</span></span>  
 <span data-ttu-id="7091a-107">태그를 사용 `<value>` 하 여 속성을 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="7091a-107">Use the `<value>` tag to describe a property.</span></span> <span data-ttu-id="7091a-108">Visual Studio 개발 환경에서 코드 마법사를 사용 하 여 속성을 추가 하면 [\<summary>](summary.md) 새 속성의 태그가 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7091a-108">Note that when you add a property using the code wizard in the Visual Studio development environment, it will add a [\<summary>](summary.md) tag for the new property.</span></span> <span data-ttu-id="7091a-109">그런 다음 `<value>` 속성이 나타내는 값을 설명 하는 태그를 수동으로 추가 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7091a-109">You should then manually add a `<value>` tag to describe the value that the property represents.</span></span>  
  
 <span data-ttu-id="7091a-110">[-Doc](../../reference/command-line-compiler/doc.md) 로 컴파일하여 문서 주석을 파일로 처리 합니다.</span><span class="sxs-lookup"><span data-stu-id="7091a-110">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="7091a-111">예제</span><span class="sxs-lookup"><span data-stu-id="7091a-111">Example</span></span>  
 <span data-ttu-id="7091a-112">이 예제에서는 태그를 사용 하 여 `<value>` 속성에 포함 된 값을 설명 합니다 `Counter` .</span><span class="sxs-lookup"><span data-stu-id="7091a-112">This example uses the `<value>` tag to describe what value the `Counter` property holds.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#1)]  
  
## <a name="see-also"></a><span data-ttu-id="7091a-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7091a-113">See also</span></span>

- [<span data-ttu-id="7091a-114">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="7091a-114">XML Comment Tags</span></span>](index.md)
