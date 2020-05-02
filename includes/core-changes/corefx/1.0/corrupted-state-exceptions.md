---
ms.openlocfilehash: 394f2daebad7b6af94bee4d7876796e87fe8ab19
ms.sourcegitcommit: 8b02d42f93adda304246a47f49f6449fc74a3af4
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2020
ms.locfileid: "82135630"
---
### <a name="handling-corrupted-state-exceptions-is-not-supported"></a><span data-ttu-id="54501-101">손상된 상태 예외 처리는 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="54501-101">Handling corrupted state exceptions is not supported</span></span>

<span data-ttu-id="54501-102">.NET Core에서 손상된 프로세스 상태 예외 처리는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54501-102">Handling corrupted-process-state exceptions in .NET Core is not supported.</span></span>

#### <a name="change-description"></a><span data-ttu-id="54501-103">변경 내용 설명</span><span class="sxs-lookup"><span data-stu-id="54501-103">Change description</span></span>

<span data-ttu-id="54501-104">이전에는 관리 코드 예외 처리기(예: C#에서 [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) 문을 사용하여)가 손상된 프로세스 상태 예외를 catch하고 처리할 수 있었습니다.</span><span class="sxs-lookup"><span data-stu-id="54501-104">Previously, corrupted-process-state exceptions could be caught and handled by managed code exception handlers, for example, by using a [try-catch](../../../../docs/csharp/language-reference/keywords/try-catch.md) statement in C#.</span></span>

<span data-ttu-id="54501-105">.NET Core 1.0부터는 손상된 프로세스 상태 예외를 관리 코드로 처리할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54501-105">Starting in .NET Core 1.0, corrupted-process-state exceptions cannot be handled by managed code.</span></span> <span data-ttu-id="54501-106">공용 언어 런타임에서는 손상된 프로세스 상태 예외를 관리 코드에 제공하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="54501-106">The common language runtime doesn't deliver corrupted-process-state exceptions to managed code.</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="54501-107">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="54501-107">Version introduced</span></span>

<span data-ttu-id="54501-108">1.0</span><span class="sxs-lookup"><span data-stu-id="54501-108">1.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="54501-109">권장 조치</span><span class="sxs-lookup"><span data-stu-id="54501-109">Recommended action</span></span>

<span data-ttu-id="54501-110">대신 발생하는 상황을 해결하여 손상된 프로세스 상태 예외를 처리할 필요가 없습니다.</span><span class="sxs-lookup"><span data-stu-id="54501-110">Avoid the need to handle corrupted-process-state exceptions by addressing the situations that lead to them instead.</span></span> <span data-ttu-id="54501-111">손상된 프로세스 상태 예외를 처리해야 하는 경우 예외 처리기를 C 또는 C++ 코드로 작성합니다.</span><span class="sxs-lookup"><span data-stu-id="54501-111">If it's absolutely necessary to handle corrupted-process-state exceptions, write the exception handler in C or C++ code.</span></span>

#### <a name="category"></a><span data-ttu-id="54501-112">범주</span><span class="sxs-lookup"><span data-stu-id="54501-112">Category</span></span>

<span data-ttu-id="54501-113">핵심 .NET 라이브러리</span><span class="sxs-lookup"><span data-stu-id="54501-113">Core .NET libraries</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="54501-114">영향을 받는 API</span><span class="sxs-lookup"><span data-stu-id="54501-114">Affected APIs</span></span>

- <xref:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute?displayProperty=fullName>
- [<span data-ttu-id="54501-115">legacyCorruptedStateExceptionsPolicy 요소</span><span class="sxs-lookup"><span data-stu-id="54501-115">legacyCorruptedStateExceptionsPolicy element</span></span>](~/docs/framework/configure-apps/file-schema/runtime/legacycorruptedstateexceptionspolicy-element.md)

<!--

#### Affected APIs

- `T:System.Runtime.ExceptionServices.HandleProcessCorruptedStateExceptionsAttribute`

-->
