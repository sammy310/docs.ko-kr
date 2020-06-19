---
title: ConnectionGroup 클래스
description: ServicePoint 컨텍스트 내에서 연결을 그룹화 하 고 .NET의 네트워크 리소스에 대 한 컨텍스트를 유지 하는 데 사용 되는 ConnectionGroup 클래스에 대해 알아봅니다.
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.ConnectionGroup
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 25c08217-fdeb-44b9-9cd6-1b4955d6e602
ms.openlocfilehash: 7121713b26880f2490b40d59d92d431a567519b3
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989815"
---
# <a name="connectiongroup-class"></a><span data-ttu-id="fd6ad-103">ConnectionGroup 클래스</span><span class="sxs-lookup"><span data-stu-id="fd6ad-103">ConnectionGroup Class</span></span>

<span data-ttu-id="fd6ad-104">`ConnectionGroup`클래스는 컨텍스트 내에서 연결 목록을 그룹화 하 <xref:System.Net.ServicePoint> 고 네트워크 리소스 (예: 프록시 및 별도의 클라이언트)의 컨텍스트를 유지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ad-104">The `ConnectionGroup` class groups a list of connections within the <xref:System.Net.ServicePoint> context and is used to maintain context for network resources (for example, proxies and separate clients).</span></span>

## <a name="syntax"></a><span data-ttu-id="fd6ad-105">구문</span><span class="sxs-lookup"><span data-stu-id="fd6ad-105">Syntax</span></span>
  
```csharp  
internal class ConnectionGroup
```

> [!WARNING]
> <span data-ttu-id="fd6ad-106">`ConnectionGroup`클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ad-106">The `ConnectionGroup` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="fd6ad-107">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ad-107">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="fd6ad-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd6ad-108">Requirements</span></span>

<span data-ttu-id="fd6ad-109">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="fd6ad-109">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="fd6ad-110">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="fd6ad-110">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="fd6ad-111">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="fd6ad-111">**.NET Framework versions:** Available since 2.0.</span></span>
