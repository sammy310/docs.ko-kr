---
description: '다음에 대 한 자세한 정보: s_isDebuggerCheckDisabledForTestPurposes 필드'
title: s_isDebuggerCheckDisabledForTestPurposes 필드
ms.date: 03/30/2017
ms.technology: dotnet-wpf
topic_type:
- apiref
api_name:
- System.Windows.Diagnostics.VisualDiagnostics.s_isDebuggerCheckDisabledForTestPurposes
api_location:
- PresentationCore.dll
api_type:
- Assembly
ms.assetid: 9033a513-c255-4f31-b6d7-09b8d8c50e2d
ms.openlocfilehash: a71235c13a7a35872bcf5374be8077bafad5ff9a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99802660"
---
# <a name="s_isdebuggercheckdisabledfortestpurposes-field"></a><span data-ttu-id="e67a9-103">s_isDebuggerCheckDisabledForTestPurposes 필드</span><span class="sxs-lookup"><span data-stu-id="e67a9-103">s_isDebuggerCheckDisabledForTestPurposes Field</span></span>

<span data-ttu-id="e67a9-104">클래스의이 전용 필드는 `System.Windows.Diagnostics.VisualDiagnostics` Visual Studio에서 활성 디버거에 대 한 내부 검사를 수행할지 여부를 결정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e67a9-104">This private field in the `System.Windows.Diagnostics.VisualDiagnostics` class is used by Visual Studio to determine whether an internal check for an active debugger will be performed.</span></span>

## <a name="syntax"></a><span data-ttu-id="e67a9-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="e67a9-105">Syntax</span></span>

```csharp
private static bool s_isDebuggerCheckDisabledForTestPurposes
```

> [!WARNING]
> <span data-ttu-id="e67a9-106">클래스의 Api `System.Windows.Diagnostics.VisualDiagnostics` 는 응용 프로그램이 디버거에서 실행 되는 경우에만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e67a9-106">APIs in the `System.Windows.Diagnostics.VisualDiagnostics` class are only available when an application is running under a debugger.</span></span> <span data-ttu-id="e67a9-107">`s_isDebuggerCheckDisabledForTestPurposes` `true` 디버거 외부에서 api에 액세스 하려면를로 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="e67a9-107">Set `s_isDebuggerCheckDisabledForTestPurposes` to `true` to access the APIs outside of a debugger.</span></span>
>
> <span data-ttu-id="e67a9-108">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 필드를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e67a9-108">Microsoft does not support the use of this field in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="e67a9-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e67a9-109">Requirements</span></span>

<span data-ttu-id="e67a9-110">**네임스페이스:** <xref:System.Windows.Diagnostics></span><span class="sxs-lookup"><span data-stu-id="e67a9-110">**Namespace:** <xref:System.Windows.Diagnostics></span></span>

<span data-ttu-id="e67a9-111">**어셈블리:** PresentationCore (PresentationCore.dll)</span><span class="sxs-lookup"><span data-stu-id="e67a9-111">**Assembly:** PresentationCore (in PresentationCore.dll)</span></span>

<span data-ttu-id="e67a9-112">**.NET Framework 버전:** 4.6부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e67a9-112">**.NET Framework versions:** Available since 4.6.</span></span>
