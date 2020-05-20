---
title: C# 프로그램의 일반적인 구조 - C# 프로그래밍 가이드
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
ms.openlocfilehash: 4a2340c29527ac09ba53daee03e06420b269df56
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/14/2020
ms.locfileid: "77673344"
---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="7f84c-102">C# 프로그램의 일반적인 구조(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="7f84c-102">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="7f84c-103">C# 프로그램은 하나 이상의 파일로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f84c-103">C# programs can consist of one or more files.</span></span> <span data-ttu-id="7f84c-104">각 파일에는 0개 이상의 네임스페이스가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f84c-104">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="7f84c-105">네임스페이스에는 다른 네임스페이스 외에 클래스, 구조체, 인터페이스, 열거형 및 대리자 같은 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7f84c-105">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="7f84c-106">다음은 이러한 모든 요소를 포함하는 C# 프로그램의 기본 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="7f84c-106">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 [!code-csharp[csProgGuide#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/class2.cs#34)]  
  
## <a name="related-sections"></a><span data-ttu-id="7f84c-107">관련 단원</span><span class="sxs-lookup"><span data-stu-id="7f84c-107">Related Sections</span></span>  
 <span data-ttu-id="7f84c-108">추가 정보</span><span class="sxs-lookup"><span data-stu-id="7f84c-108">For more information:</span></span>  
  
- [<span data-ttu-id="7f84c-109">클래스</span><span class="sxs-lookup"><span data-stu-id="7f84c-109">Classes</span></span>](../classes-and-structs/classes.md)  
  
- [<span data-ttu-id="7f84c-110">구조체</span><span class="sxs-lookup"><span data-stu-id="7f84c-110">Structs</span></span>](../../language-reference/builtin-types/struct.md)  
  
- [<span data-ttu-id="7f84c-111">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="7f84c-111">Namespaces</span></span>](../namespaces/index.md)  
  
- [<span data-ttu-id="7f84c-112">인터페이스</span><span class="sxs-lookup"><span data-stu-id="7f84c-112">Interfaces</span></span>](../interfaces/index.md)  
  
- [<span data-ttu-id="7f84c-113">대리자</span><span class="sxs-lookup"><span data-stu-id="7f84c-113">Delegates</span></span>](../delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="7f84c-114">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="7f84c-114">C# Language Specification</span></span>  

<span data-ttu-id="7f84c-115">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [기본 개념](~/_csharplang/spec/basic-concepts.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="7f84c-115">For more information, see [Basic concepts](~/_csharplang/spec/basic-concepts.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="7f84c-116">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7f84c-116">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7f84c-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7f84c-117">See also</span></span>

- [<span data-ttu-id="7f84c-118">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="7f84c-118">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="7f84c-119">C# 프로그램 내부</span><span class="sxs-lookup"><span data-stu-id="7f84c-119">Inside a C# Program</span></span>](./index.md)
- [<span data-ttu-id="7f84c-120">C# 참조</span><span class="sxs-lookup"><span data-stu-id="7f84c-120">C# Reference</span></span>](../../language-reference/index.md)
