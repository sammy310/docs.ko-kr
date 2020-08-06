---
title: C# 프로그램의 일반적인 구조 - C# 프로그래밍 가이드
description: C# 프로그램에 필요한 모든 요소를 포함하는 기본 구조 프로그램을 사용하여 프로그램 구조에 대해 알아봅니다.
ms.date: 07/20/2015
helpviewer_keywords:
- C# language, program structure
ms.assetid: 5ae964a5-0ef0-40fe-88fb-6d1793371d0d
ms.openlocfilehash: 1d7662d18acee60050800eaf3873cd1c11ef5157
ms.sourcegitcommit: 6f58a5f75ceeb936f8ee5b786e9adb81a9a3bee9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2020
ms.locfileid: "87301842"
---
# <a name="general-structure-of-a-c-program-c-programming-guide"></a><span data-ttu-id="48b63-103">C# 프로그램의 일반적인 구조(C# 프로그래밍 가이드)</span><span class="sxs-lookup"><span data-stu-id="48b63-103">General Structure of a C# Program (C# Programming Guide)</span></span>
<span data-ttu-id="48b63-104">C# 프로그램은 하나 이상의 파일로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="48b63-104">C# programs can consist of one or more files.</span></span> <span data-ttu-id="48b63-105">각 파일에는 0개 이상의 네임스페이스가 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48b63-105">Each file can contain zero or more namespaces.</span></span> <span data-ttu-id="48b63-106">네임스페이스에는 다른 네임스페이스 외에 클래스, 구조체, 인터페이스, 열거형 및 대리자 같은 형식이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="48b63-106">A namespace can contain types such as classes, structs, interfaces, enumerations, and delegates, in addition to other namespaces.</span></span> <span data-ttu-id="48b63-107">다음은 이러한 모든 요소를 포함하는 C# 프로그램의 기본 구조입니다.</span><span class="sxs-lookup"><span data-stu-id="48b63-107">The following is the skeleton of a C# program that contains all of these elements.</span></span>  
  
 [!code-csharp[csProgGuide#34](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuide/CS/class2.cs#34)]  
  
## <a name="related-sections"></a><span data-ttu-id="48b63-108">관련 단원</span><span class="sxs-lookup"><span data-stu-id="48b63-108">Related Sections</span></span>  
 <span data-ttu-id="48b63-109">추가 정보</span><span class="sxs-lookup"><span data-stu-id="48b63-109">For more information:</span></span>  
  
- [<span data-ttu-id="48b63-110">클래스</span><span class="sxs-lookup"><span data-stu-id="48b63-110">Classes</span></span>](../classes-and-structs/classes.md)  
  
- [<span data-ttu-id="48b63-111">구조체</span><span class="sxs-lookup"><span data-stu-id="48b63-111">Structs</span></span>](../../language-reference/builtin-types/struct.md)  
  
- [<span data-ttu-id="48b63-112">네임스페이스</span><span class="sxs-lookup"><span data-stu-id="48b63-112">Namespaces</span></span>](../namespaces/index.md)  
  
- [<span data-ttu-id="48b63-113">인터페이스</span><span class="sxs-lookup"><span data-stu-id="48b63-113">Interfaces</span></span>](../interfaces/index.md)  
  
- [<span data-ttu-id="48b63-114">대리자</span><span class="sxs-lookup"><span data-stu-id="48b63-114">Delegates</span></span>](../delegates/index.md)  
  
## <a name="c-language-specification"></a><span data-ttu-id="48b63-115">C# 언어 사양</span><span class="sxs-lookup"><span data-stu-id="48b63-115">C# Language Specification</span></span>  

<span data-ttu-id="48b63-116">자세한 내용은 [C# 언어 사양](/dotnet/csharp/language-reference/language-specification/introduction)의 [기본 개념](~/_csharplang/spec/basic-concepts.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="48b63-116">For more information, see [Basic concepts](~/_csharplang/spec/basic-concepts.md) in the [C# Language Specification](/dotnet/csharp/language-reference/language-specification/introduction).</span></span> <span data-ttu-id="48b63-117">언어 사양은 C# 구문 및 사용법에 대 한 신뢰할 수 있는 소스 됩니다.</span><span class="sxs-lookup"><span data-stu-id="48b63-117">The language specification is the definitive source for C# syntax and usage.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="48b63-118">참고 항목</span><span class="sxs-lookup"><span data-stu-id="48b63-118">See also</span></span>

- [<span data-ttu-id="48b63-119">C# 프로그래밍 가이드</span><span class="sxs-lookup"><span data-stu-id="48b63-119">C# Programming Guide</span></span>](../index.md)
- [<span data-ttu-id="48b63-120">C# 프로그램 내용</span><span class="sxs-lookup"><span data-stu-id="48b63-120">Inside a C# Program</span></span>](./index.md)
- [<span data-ttu-id="48b63-121">C# 참조</span><span class="sxs-lookup"><span data-stu-id="48b63-121">C# Reference</span></span>](../../language-reference/index.md)
