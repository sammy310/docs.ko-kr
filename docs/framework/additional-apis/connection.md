---
title: Connection 클래스
ms.date: 05/01/2017
topic_type:
- apiref
api_name:
- System.Net.Connection
api_location:
- System.dll
api_type:
- Assembly
ms.assetid: 6f0b8902-f31c-4ab9-a8c9-de43228995ec
author: rpetrusha
ms.author: mairaw
ms.openlocfilehash: c50f673e77ef384ccf33803e14d60c322b6c0365
ms.sourcegitcommit: 621a5f6df00152006160987395b93b5b55f7ffcd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2019
ms.locfileid: "66300971"
---
# <a name="connection-class"></a><span data-ttu-id="cd03d-102">Connection 클래스</span><span class="sxs-lookup"><span data-stu-id="cd03d-102">Connection Class</span></span>

<span data-ttu-id="cd03d-103">`Connection` 클래스 구문 분석 서버 응답, 큐 요청 및 요청 파이프라인.</span><span class="sxs-lookup"><span data-stu-id="cd03d-103">The `Connection` class parses server responses, queue requests, and pipeline requests.</span></span>

## <a name="syntax"></a><span data-ttu-id="cd03d-104">구문</span><span class="sxs-lookup"><span data-stu-id="cd03d-104">Syntax</span></span>
  
```csharp  
internal class Connection : PooledStream
```

> [!WARNING]
> <span data-ttu-id="cd03d-105">`Connection` 클래스는 내부용 이며 사용자 코드에서 직접 사용할 하려고 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd03d-105">The `Connection` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="cd03d-106">Microsoft는 어떤 상황에서 프로덕션 응용 프로그램에서이 클래스의 사용을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cd03d-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="cd03d-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="cd03d-107">Requirements</span></span>

<span data-ttu-id="cd03d-108">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="cd03d-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="cd03d-109">**어셈블리:** 시스템 (에: System.dll)</span><span class="sxs-lookup"><span data-stu-id="cd03d-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="cd03d-110">**.NET framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cd03d-110">**.NET Framework versions:** Available since 2.0.</span></span>
