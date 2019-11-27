---
title: Connection 클래스 (System.Net)
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: b3045e9f6a4b3d86580ec3bc5719520fed7d3a35
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74429354"
---
# <a name="connection-class"></a><span data-ttu-id="9563f-102">Connection 클래스</span><span class="sxs-lookup"><span data-stu-id="9563f-102">Connection Class</span></span>

<span data-ttu-id="9563f-103">`Connection` 클래스는 서버 응답, 큐 요청 및 파이프라인 요청을 구문 분석 합니다.</span><span class="sxs-lookup"><span data-stu-id="9563f-103">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="9563f-104">구문</span><span class="sxs-lookup"><span data-stu-id="9563f-104">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="9563f-105">`Connection` 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="9563f-105">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="9563f-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="9563f-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="9563f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9563f-107">Requirements</span></span>

<span data-ttu-id="9563f-108">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="9563f-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="9563f-109">**어셈블리:** 시스템 (system.string)</span><span class="sxs-lookup"><span data-stu-id="9563f-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="9563f-110">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="9563f-110">**.NET Framework versions:** Available since 2.0.</span></span>
