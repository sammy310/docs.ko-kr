---
title: Interop 관련 호환성이 손상되는 변경
description: .NET Core 및 .NET 5.0 이상에서 interop 관련 호환성이 손상되는 변경 내용을 나열합니다.
ms.date: 06/23/2020
ms.openlocfilehash: bac60631f8515eaf102f9d6e75fe817baceb7824
ms.sourcegitcommit: 7476c20d2f911a834a00b8a7f5e8926bae6804d9
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/11/2020
ms.locfileid: "88062428"
---
# <a name="interop-breaking-changes"></a><span data-ttu-id="c50e9-103">Interop 관련 호환성이 손상되는 변경</span><span class="sxs-lookup"><span data-stu-id="c50e9-103">Interop breaking changes</span></span>

<span data-ttu-id="c50e9-104">이 페이지에는 다음과 같은 주요 변경 사항이 설명되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="c50e9-104">The following breaking changes are documented on this page:</span></span>

| <span data-ttu-id="c50e9-105">주요 변경 내용</span><span class="sxs-lookup"><span data-stu-id="c50e9-105">Breaking change</span></span> | <span data-ttu-id="c50e9-106">도입된 버전</span><span class="sxs-lookup"><span data-stu-id="c50e9-106">Version introduced</span></span> |
| - | :-: |
| [<span data-ttu-id="c50e9-107">비 Windows 플랫폼에서 A/W 접미사 검색 안 함</span><span class="sxs-lookup"><span data-stu-id="c50e9-107">No A/W suffix probing on non-Windows platforms</span></span>](#no-aw-suffix-probing-on-non-windows-platforms) | <span data-ttu-id="c50e9-108">5.0</span><span class="sxs-lookup"><span data-stu-id="c50e9-108">5.0</span></span> |
| [<span data-ttu-id="c50e9-109">WinRT의 기본 제공 지원이 .NET에서 제거됨</span><span class="sxs-lookup"><span data-stu-id="c50e9-109">Built-in support for WinRT is removed from .NET</span></span>](#built-in-support-for-winrt-is-removed-from-net) | <span data-ttu-id="c50e9-110">5.0</span><span class="sxs-lookup"><span data-stu-id="c50e9-110">5.0</span></span> |

## <a name="net-50"></a><span data-ttu-id="c50e9-111">.NET 5.0</span><span class="sxs-lookup"><span data-stu-id="c50e9-111">.NET 5.0</span></span>

[!INCLUDE [function-suffix-pinvoke](../../../includes/core-changes/interop/5.0/function-suffix-pinvoke.md)]

***

[!INCLUDE [built-in-support-for-winrt-removed](~/includes/core-changes/interop/5.0/built-in-support-for-winrt-removed.md)]

***
