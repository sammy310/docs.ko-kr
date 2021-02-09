---
description: '자세한 정보: <inheritdoc>(C# 프로그래밍 가이드)'
title: <inheritdoc> - C# 프로그래밍 가이드
ms.date: 01/21/2020
f1_keywords:
- inheritdoc
- <inheritdoc>
helpviewer_keywords:
- <inheritdoc> C# XML tag
- inheritdoc C# XML tag
ms.assetid: 46d329b1-5b84-4537-9e17-73ca97313e4e
ms.openlocfilehash: 960bdfbcec1e3f6a89675273f63b6d398e44947e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99719398"
---
# <a name="inheritdoc-c-programming-guide"></a><span data-ttu-id="0a865-103">\<inheritdoc>(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="0a865-103">\<inheritdoc> (C# Programming Guide)</span></span>

## <a name="syntax"></a><span data-ttu-id="0a865-104">구문</span><span class="sxs-lookup"><span data-stu-id="0a865-104">Syntax</span></span>  
  
```xml  
<inheritdoc/>
```  

## <a name="inheritdoc"></a><span data-ttu-id="0a865-105">InheritDoc</span><span class="sxs-lookup"><span data-stu-id="0a865-105">InheritDoc</span></span>

<span data-ttu-id="0a865-106">기본 클래스, 인터페이스 및 유사한 메서드에서 XML 주석을 상속합니다.</span><span class="sxs-lookup"><span data-stu-id="0a865-106">Inherit XML comments from base classes, interfaces, and similar methods.</span></span> <span data-ttu-id="0a865-107">이렇게 하면 중복 XML 주석을 복사하여 붙여 넣을 필요가 없으며 XML 주석이 자동으로 동기화됩니다.</span><span class="sxs-lookup"><span data-stu-id="0a865-107">This eliminates unwanted copying and pasting of duplicate XML comments and automatically keeps XML comments synchronized.</span></span>
  
## <a name="remarks"></a><span data-ttu-id="0a865-108">설명</span><span class="sxs-lookup"><span data-stu-id="0a865-108">Remarks</span></span>  

<span data-ttu-id="0a865-109">기본 클래스 또는 인터페이스에 XML 주석을 추가하고 InheritDoc가 주석을 구현 클래스에 복사하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a865-109">Add your XML comments in base classes or interfaces and let InheritDoc copy the comments to implementing classes.</span></span>

<span data-ttu-id="0a865-110">동기 메서드에 XML 주석을 추가하고 InheritDoc가 동일한 메서드의 비동기 버전에 주석을 복사하도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="0a865-110">Add your XML comments to your synchronous methods and let InheritDoc copy the comments to your asynchronous versions of the same methods.</span></span>  

<span data-ttu-id="0a865-111">특정 멤버에서 주석을 복사하려면 `cref` 특성을 사용하여 멤버를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0a865-111">If you want to copy the comments from a specific member you can use the `cref` attribute to specify the member.</span></span>
  
## <a name="examples"></a><span data-ttu-id="0a865-112">예</span><span class="sxs-lookup"><span data-stu-id="0a865-112">Examples</span></span>

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#16)]  

[!code-csharp[csProgGuideDocComments#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideDocComments/CS/DocComments.cs#17)]  

## <a name="see-also"></a><span data-ttu-id="0a865-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="0a865-113">See also</span></span>

- [<span data-ttu-id="0a865-114">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="0a865-114">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="0a865-115">문서 주석에 대한 권장 태그</span><span class="sxs-lookup"><span data-stu-id="0a865-115">Recommended Tags for Documentation Comments</span></span>](./recommended-tags-for-documentation-comments.md)
