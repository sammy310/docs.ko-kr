---
description: '자세한 정보: ServicePointManager 메서드'
title: ServicePointManager 메서드 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.ServicePointManager.CloseConnectionGroups
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 8cd1a1f0f4dbdaeaee117e6a7ae4219680363a6e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99699560"
---
# <a name="servicepointmanagercloseconnectiongroups-method"></a><span data-ttu-id="64352-103">ServicePointManager 메서드</span><span class="sxs-lookup"><span data-stu-id="64352-103">ServicePointManager.CloseConnectionGroups method</span></span>

<span data-ttu-id="64352-104">모든 서비스 요소를 반복 하 고 지정 된 이름이 있는 연결 그룹을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="64352-104">Iterates through all service points and closes connection groups that have the specified name.</span></span>

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> <span data-ttu-id="64352-105">이 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="64352-105">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="64352-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="64352-106">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="64352-107">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64352-107">Parameters</span></span>

<span data-ttu-id="64352-108">`connectionGroupName` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="64352-108">`connectionGroupName` <xref:System.String></span></span>

<span data-ttu-id="64352-109">닫을 연결 그룹의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="64352-109">The name of the connection group to close.</span></span>

## <a name="requirements"></a><span data-ttu-id="64352-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64352-110">Requirements</span></span>

<span data-ttu-id="64352-111">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="64352-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="64352-112">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="64352-112">**Assembly:** System (in System.dll)</span></span>
