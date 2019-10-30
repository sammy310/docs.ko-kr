---
title: ConnectionGroup 클래스
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 5a9041ab75836b4239d492987e94c9104133e9bf
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73120044"
---
# <a name="connectiongroup-class"></a><span data-ttu-id="ecd0f-102">ConnectionGroup 클래스</span><span class="sxs-lookup"><span data-stu-id="ecd0f-102">ConnectionGroup Class</span></span>

<span data-ttu-id="ecd0f-103">`ConnectionGroup` 클래스는 <xref:System.Net.ServicePoint> 컨텍스트 내에서 연결 목록을 그룹화 하 고 네트워크 리소스 (예: 프록시 및 별도의 클라이언트)의 컨텍스트를 유지 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ecd0f-103">The `ConnectionGroup` class groups a list of connections within the <xref:System.Net.ServicePoint> context and is used to maintain context for network resources (for example, proxies and separate clients).</span></span>

## <a name="syntax"></a><span data-ttu-id="ecd0f-104">구문</span><span class="sxs-lookup"><span data-stu-id="ecd0f-104">Syntax</span></span>
  
```csharp  
internal class ConnectionGroup
```

> [!WARNING]
> <span data-ttu-id="ecd0f-105">`ConnectionGroup` 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="ecd0f-105">The `ConnectionGroup` class is internal and is not meant to be used directly in your code.</span></span>
> 
> <span data-ttu-id="ecd0f-106">Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="ecd0f-106">Microsoft does not support the use of this class in a production application under any circumstance.</span></span>

## <a name="requirements"></a><span data-ttu-id="ecd0f-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ecd0f-107">Requirements</span></span>

<span data-ttu-id="ecd0f-108">**네임스페이스:** <xref:System.Net></span><span class="sxs-lookup"><span data-stu-id="ecd0f-108">**Namespace:** <xref:System.Net></span></span>

<span data-ttu-id="ecd0f-109">**어셈블리:** 시스템 (system.string)</span><span class="sxs-lookup"><span data-stu-id="ecd0f-109">**Assembly:** System (in System.dll)</span></span>

<span data-ttu-id="ecd0f-110">**.NET Framework 버전:** 2.0부터 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="ecd0f-110">**.NET Framework versions:** Available since 2.0.</span></span>
