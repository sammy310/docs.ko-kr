---
title: 컴파일 구성 설정
description: .NET Core 앱에 대해 JIT 컴파일러가 작동하는 방식을 구성하는 런타임 설정에 대해 알아봅니다.
ms.date: 11/27/2019
ms.topic: reference
ms.openlocfilehash: bcc445b6edc48d9432ee614b0b19c9c25621f4a0
ms.sourcegitcommit: 32a575bf4adccc901f00e264f92b759ced633379
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2019
ms.locfileid: "74998878"
---
# <a name="run-time-configuration-options-for-compilation"></a><span data-ttu-id="137ee-103">컴파일을 위한 런타임 구성 옵션</span><span class="sxs-lookup"><span data-stu-id="137ee-103">Run-time configuration options for compilation</span></span>

## <a name="tiered-compilation"></a><span data-ttu-id="137ee-104">계층화된 컴파일</span><span class="sxs-lookup"><span data-stu-id="137ee-104">Tiered compilation</span></span>

- <span data-ttu-id="137ee-105">JIT 컴파일러가 [계층화된 컴파일](../whats-new/dotnet-core-3-0.md#tiered-compilation)을 사용하는지 여부를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="137ee-105">Configures whether the JIT compiler uses [tiered compilation](../whats-new/dotnet-core-3-0.md#tiered-compilation).</span></span>
- <span data-ttu-id="137ee-106">.NET Core 3.0 이상에서는 기본적으로 계층화된 컴파일이 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="137ee-106">In .NET Core 3.0 and later, tiered compilation is enabled by default.</span></span>
- <span data-ttu-id="137ee-107">.NET Core 2.1 및 2.2에서는 기본적으로 계층화된 컴파일이 사용하지 않도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="137ee-107">In .NET Core 2.1 and 2.2, tiered compilation is disabled by default.</span></span>

| | <span data-ttu-id="137ee-108">설정 이름</span><span class="sxs-lookup"><span data-stu-id="137ee-108">Setting name</span></span> | <span data-ttu-id="137ee-109">값</span><span class="sxs-lookup"><span data-stu-id="137ee-109">Values</span></span> |
| - | - | - |
| <span data-ttu-id="137ee-110">**runtimeconfig.json**</span><span class="sxs-lookup"><span data-stu-id="137ee-110">**runtimeconfig.json**</span></span> | `System.Runtime.TieredCompilation` | <span data-ttu-id="137ee-111">`true` - 사용</span><span class="sxs-lookup"><span data-stu-id="137ee-111">`true` - enabled</span></span><br/><span data-ttu-id="137ee-112">`false` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="137ee-112">`false` - disabled</span></span> |
| <span data-ttu-id="137ee-113">**환경 변수**</span><span class="sxs-lookup"><span data-stu-id="137ee-113">**Environment variable**</span></span> | `COMPlus_TieredCompilation` | <span data-ttu-id="137ee-114">`1` - 사용</span><span class="sxs-lookup"><span data-stu-id="137ee-114">`1` - enabled</span></span><br/><span data-ttu-id="137ee-115">`0` - 사용 안 함</span><span class="sxs-lookup"><span data-stu-id="137ee-115">`0` - disabled</span></span> |
