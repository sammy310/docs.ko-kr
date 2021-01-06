---
title: SYSLIB0008 경고
description: 컴파일 시간 경고 SYSLIB0008을 생성하는 사용되지 않음에 대해 알아봅니다.
ms.topic: reference
ms.date: 10/20/2020
ms.openlocfilehash: 2b573f4b28cdf79107395f5cb38a4226d0ccc11e
ms.sourcegitcommit: e301979e3049ce412d19b094c60ed95b316a8f8c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/16/2020
ms.locfileid: "97596335"
---
# <a name="syslib0008-createpdbgenerator-is-not-supported"></a><span data-ttu-id="899b0-103">SYSLIB0008: CreatePdbGenerator가 지원되지 않음</span><span class="sxs-lookup"><span data-stu-id="899b0-103">SYSLIB0008: CreatePdbGenerator is not supported</span></span>

<span data-ttu-id="899b0-104"><xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> API는 .NET 5.0부터 사용되지 않는 것으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="899b0-104">The <xref:System.Runtime.CompilerServices.DebugInfoGenerator.CreatePdbGenerator?displayProperty=nameWithType> API is marked obsolete, starting in .NET 5.0.</span></span> <span data-ttu-id="899b0-105">이 API를 사용하면 컴파일 시간에 `SYSLIB0008` 경고가 생성됩니다.</span><span class="sxs-lookup"><span data-stu-id="899b0-105">Using this API generates warning `SYSLIB0008` at compile time.</span></span>

## <a name="suppress-the-warning"></a><span data-ttu-id="899b0-106">경고를 표시하지 않음</span><span class="sxs-lookup"><span data-stu-id="899b0-106">Suppress the warning</span></span>

<span data-ttu-id="899b0-107">코드를 변경할 수 없는 경우 `#pragma` 지시문 또는 `<NoWarn>` 프로젝트 설정을 통해 경고를 표시하지 않을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="899b0-107">If you cannot change your code, you can suppress the warning through a `#pragma` directive or a `<NoWarn>` project setting.</span></span> <span data-ttu-id="899b0-108">예제는 [경고 표시 안 함](../syslib-obsoletions.md#suppress-warnings)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="899b0-108">For examples, see [Suppress warnings](../syslib-obsoletions.md#suppress-warnings).</span></span>
