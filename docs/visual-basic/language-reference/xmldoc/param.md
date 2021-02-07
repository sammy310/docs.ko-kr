---
description: 다음에 대해 자세히 알아보세요. <param> (Visual Basic)
title: <param>
ms.date: 07/20/2015
helpviewer_keywords:
- param XML tag
- <param> XML tag
ms.assetid: 4e32e86f-f6f3-4301-b7fc-2f321fb54368
ms.openlocfilehash: 94fe5e11d5846f7fa00eb73c1c4363990ae23b2f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99700294"
---
# <a name="param-visual-basic"></a><span data-ttu-id="2c28b-103">\<param>(Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="2c28b-103">\<param> (Visual Basic)</span></span>

<span data-ttu-id="2c28b-104">매개 변수 이름 및 설명을 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c28b-104">Defines a parameter name and description.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2c28b-105">구문</span><span class="sxs-lookup"><span data-stu-id="2c28b-105">Syntax</span></span>  
  
```xml  
<param name="name">description</param>  
```  
  
## <a name="parameters"></a><span data-ttu-id="2c28b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2c28b-106">Parameters</span></span>  

 `name`  
 <span data-ttu-id="2c28b-107">메서드 매개 변수의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="2c28b-107">The name of a method parameter.</span></span> <span data-ttu-id="2c28b-108">이름을 큰따옴표(“ ”)로 묶습니다.</span><span class="sxs-lookup"><span data-stu-id="2c28b-108">Enclose the name in double quotation marks (" ").</span></span>  
  
 `description`  
 <span data-ttu-id="2c28b-109">매개 변수에 대한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="2c28b-109">A description for the parameter.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="2c28b-110">설명</span><span class="sxs-lookup"><span data-stu-id="2c28b-110">Remarks</span></span>  

 <span data-ttu-id="2c28b-111">`<param>` 태그는 메서드의 매개 변수 중 하나를 설명하기 위해 메서드 선언에 대한 주석에서 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2c28b-111">The `<param>` tag should be used in the comment for a method declaration to describe one of the parameters for the method.</span></span>  
  
 <span data-ttu-id="2c28b-112">태그에 대 한 텍스트는 `<param>` 다음 위치에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="2c28b-112">The text for the `<param>` tag will appear in the following locations:</span></span>  
  
- <span data-ttu-id="2c28b-113">IntelliSense의 매개 변수 정보입니다.</span><span class="sxs-lookup"><span data-stu-id="2c28b-113">Parameter Info of IntelliSense.</span></span> <span data-ttu-id="2c28b-114">자세한 내용은 [Using IntelliSense](/visualstudio/ide/using-intellisense)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2c28b-114">For more information, see [Using IntelliSense](/visualstudio/ide/using-intellisense).</span></span>  
  
- <span data-ttu-id="2c28b-115">개체 브라우저.</span><span class="sxs-lookup"><span data-stu-id="2c28b-115">Object Browser.</span></span> <span data-ttu-id="2c28b-116">자세한 내용은 [코드 구조 보기](/visualstudio/ide/viewing-the-structure-of-code)를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="2c28b-116">For more information, see [Viewing the Structure of Code](/visualstudio/ide/viewing-the-structure-of-code).</span></span>  
  
 <span data-ttu-id="2c28b-117">[-doc](../../reference/command-line-compiler/doc.md)로 컴파일하여 문서 주석을 파일로 처리합니다.</span><span class="sxs-lookup"><span data-stu-id="2c28b-117">Compile with [-doc](../../reference/command-line-compiler/doc.md) to process documentation comments to a file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="2c28b-118">예제</span><span class="sxs-lookup"><span data-stu-id="2c28b-118">Example</span></span>  

 <span data-ttu-id="2c28b-119">이 예제에서는 태그를 사용 하 여 `<param>` 매개 변수를 설명 합니다 `id` .</span><span class="sxs-lookup"><span data-stu-id="2c28b-119">This example uses the `<param>` tag to describe the `id` parameter.</span></span>  
  
 [!code-vb[VbVbcnXmlDocComments#6](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnXmlDocComments/VB/Class1.vb#6)]  
  
## <a name="see-also"></a><span data-ttu-id="2c28b-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2c28b-120">See also</span></span>

- [<span data-ttu-id="2c28b-121">XML 주석 태그</span><span class="sxs-lookup"><span data-stu-id="2c28b-121">XML Comment Tags</span></span>](index.md)
