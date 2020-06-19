---
title: Connection 클래스 (System.Net)
description: .NET의 연결 클래스에 대해 알아봅니다. 이 클래스는 서버 응답, 큐 요청 및 파이프라인 요청을 구문 분석 합니다. System.NET 네임 스페이스에 있습니다.
ms.date: 05/01/2017
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Connection
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 6f0b8902-f31c-4ab9-a8c9-de43228995ec
ms.openlocfilehash: cb28724ed782fc5395dc74e9c59249ebdea44ddf
ms.sourcegitcommit: 45c8eed045779b70a47b23169897459d0323dc89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/18/2020
ms.locfileid: "84989833"
---
# <a name="connection-class"></a><span data-ttu-id="70833-105">Connection 클래스</span><span class="sxs-lookup"><span data-stu-id="70833-105">Connection Class</span></span>

<span data-ttu-id="70833-106">`Connection`클래스는 서버 응답, 큐 요청 및 파이프라인 요청을 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="70833-106">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="70833-107">구문</span><span class="sxs-lookup"><span data-stu-id="70833-107">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="70833-108">`Connection`클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="70833-108">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
>
> <span data-ttu-id="70833-109">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70833-109">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="70833-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70833-110">Requirements</span></span>

<span data-ttu-id="70833-111">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="70833-111">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="70833-112">**어셈블리:** 시스템 (System.dll)</span><span class="sxs-lookup"><span data-stu-id="70833-112">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="70833-113">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70833-113">**.NET Framework versions:** Available since 2.0.</span></span>
