---
title: 예외 처리
description: 에서 F# 예외 처리의 기본 사항을 알아보고 예외 처리 식 및 함수에 대 한 링크를 찾습니다.
ms.date: 05/16/2016
ms.openlocfilehash: e34a65dd7da9d706153254ac28e729de0745e4d0
ms.sourcegitcommit: 14ad34f7c4564ee0f009acb8bfc0ea7af3bc9541
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/01/2019
ms.locfileid: "73423067"
---
# <a name="exception-handling"></a><span data-ttu-id="04017-103">예외 처리</span><span class="sxs-lookup"><span data-stu-id="04017-103">Exception Handling</span></span>

<span data-ttu-id="04017-104">이 섹션에서는 F# 언어의 예외 처리 지원에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04017-104">This section contains information about exception handling support in the F# language.</span></span>

## <a name="exception-handling-basics"></a><span data-ttu-id="04017-105">예외 처리 기본 사항</span><span class="sxs-lookup"><span data-stu-id="04017-105">Exception Handling Basics</span></span>

<span data-ttu-id="04017-106">예외 처리는 .NET Framework의 오류 조건을 처리하는 표준 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="04017-106">Exception handling is the standard way of handling error conditions in the .NET Framework.</span></span> <span data-ttu-id="04017-107">따라서 F#을 비롯한 모든 .NET 언어는 이 메커니즘을 지원해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="04017-107">Thus, any .NET language must support this mechanism, including F#.</span></span> <span data-ttu-id="04017-108">*예외*는 오류에 대한 정보를 캡슐화하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="04017-108">An *exception* is an object that encapsulates information about an error.</span></span> <span data-ttu-id="04017-109">오류가 발생하면 예외가 발생하고 정상적인 실행이 중지됩니다.</span><span class="sxs-lookup"><span data-stu-id="04017-109">When errors occur, exceptions are raised and regular execution stops.</span></span> <span data-ttu-id="04017-110">대신, 런타임에서 예외에 대한 적절한 처리기를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="04017-110">Instead, the runtime searches for an appropriate handler for the exception.</span></span> <span data-ttu-id="04017-111">검색은 현재 함수에서 시작하고, 일치하는 처리기를 찾을 때까지 호출자의 계층을 통해 스택을 나아갑니다.</span><span class="sxs-lookup"><span data-stu-id="04017-111">The search starts in the current function, and proceeds up the stack through the layers of callers until a matching handler is found.</span></span> <span data-ttu-id="04017-112">그런 다음 처리기가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="04017-112">Then the handler is executed.</span></span>

<span data-ttu-id="04017-113">또한 스택이 해제될 때, 런타임이 `finally` 블록에서 모든 코드를 실행하여 해제 프로세스 중 개체가 올바르게 정리되도록 보장합니다.</span><span class="sxs-lookup"><span data-stu-id="04017-113">In addition, as the stack is unwound, the runtime executes any code in `finally` blocks, to guarantee that objects are cleaned up correctly during the unwinding process.</span></span>

## <a name="related-topics"></a><span data-ttu-id="04017-114">관련 항목</span><span class="sxs-lookup"><span data-stu-id="04017-114">Related Topics</span></span>

|<span data-ttu-id="04017-115">제목</span><span class="sxs-lookup"><span data-stu-id="04017-115">Title</span></span>|<span data-ttu-id="04017-116">설명</span><span class="sxs-lookup"><span data-stu-id="04017-116">Description</span></span>|
|-----|-----------|
|[<span data-ttu-id="04017-117">예외 형식</span><span class="sxs-lookup"><span data-stu-id="04017-117">Exception Types</span></span>](exception-types.md)|<span data-ttu-id="04017-118">예외 형식을 선언하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04017-118">Describes how to declare an exception type.</span></span>|
|[<span data-ttu-id="04017-119">예외: `try...with` 식</span><span class="sxs-lookup"><span data-stu-id="04017-119">Exceptions: The `try...with` Expression</span></span>](the-try-with-expression.md)|<span data-ttu-id="04017-120">예외 처리를 지원하는 언어 구문에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04017-120">Describes the language construct that supports exception handling.</span></span>|
|[<span data-ttu-id="04017-121">예외: `try...finally` 식</span><span class="sxs-lookup"><span data-stu-id="04017-121">Exceptions: The `try...finally` Expression</span></span>](the-try-finally-expression.md)|<span data-ttu-id="04017-122">예외가 throw될 때 스택이 해제되므로 정리 코드를 실행할 수 있는 언어 구문에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04017-122">Describes the language construct that enables you to execute clean-up code as the stack unwinds when an exception is thrown.</span></span>|
|[<span data-ttu-id="04017-123">예외: `raise` 함수</span><span class="sxs-lookup"><span data-stu-id="04017-123">Exceptions: the `raise` Function</span></span>](the-raise-Function.md)|<span data-ttu-id="04017-124">예외 개체를 throw하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04017-124">Describes how to throw an exception object.</span></span>|
|[<span data-ttu-id="04017-125">예외: `failwith` 함수</span><span class="sxs-lookup"><span data-stu-id="04017-125">Exceptions: The `failwith` Function</span></span>](the-failwith-function.md)|<span data-ttu-id="04017-126">일반 F# 예외를 생성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04017-126">Describes how to generate a general F# exception.</span></span>|
|[<span data-ttu-id="04017-127">예외: `invalidArg` 함수</span><span class="sxs-lookup"><span data-stu-id="04017-127">Exceptions: The `invalidArg` Function</span></span>](the-invalidArg-function.md)|<span data-ttu-id="04017-128">잘못된 인수 예외를 생성하는 방법에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="04017-128">Describes how to generate an invalid argument exception.</span></span>|
