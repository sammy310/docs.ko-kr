---
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
ms.openlocfilehash: aae9a389ae35e249d43c9dc830a68ec32cf4afef
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84990467"
---
# <a name="servicepointmanagercloseconnectiongroups-method"></a><span data-ttu-id="a63cc-102">ServicePointManager 메서드</span><span class="sxs-lookup"><span data-stu-id="a63cc-102">ServicePointManager.CloseConnectionGroups method</span></span>

<span data-ttu-id="a63cc-103">모든 서비스 요소를 반복 하 고 지정 된 이름이 있는 연결 그룹을 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="a63cc-103">Iterates through all service points and closes connection groups that have the specified name.</span></span>

```csharp
internal static void CloseConnectionGroups(string connectionGroupName)
```

> [!WARNING]
> <span data-ttu-id="a63cc-104">이 메서드는 내부 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="a63cc-104">This method is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="a63cc-105">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 방법을 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="a63cc-105">Microsoft does not support the use of this method in a production application under any circumstance.</span></span>

## <a name="parameters"></a><span data-ttu-id="a63cc-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a63cc-106">Parameters</span></span>

<span data-ttu-id="a63cc-107">`connectionGroupName` <xref:System.String></span><span class="sxs-lookup"><span data-stu-id="a63cc-107">`connectionGroupName` <xref:System.String></span></span>

<span data-ttu-id="a63cc-108">닫을 연결 그룹의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="a63cc-108">The name of the connection group to close.</span></span>

## <a name="requirements"></a><span data-ttu-id="a63cc-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a63cc-109">Requirements</span></span>

<span data-ttu-id="a63cc-110">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="a63cc-110">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="a63cc-111">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="a63cc-111">**Assembly:** System (in System.dll)</span></span>
