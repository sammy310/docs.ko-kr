---
title: CoreClrDebugRuntimeInfo 구조체
ms.date: 03/30/2017
api_name:
- CoreClrDebugRuntimeInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugRuntimeInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreDebugRuntimeInfo structure
- Silverlight, remote debugging
ms.assetid: bd01c30f-b7a8-4179-9497-622b6599b1a6
topic_type:
- apiref
ms.openlocfilehash: 92a814d427fcf2e40c7f79e9eb9192e0b7eed4b2
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132136"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="be95d-102">CoreClrDebugRuntimeInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="be95d-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="be95d-103">원격 컴퓨터의 프로세스에서 로드된 CLR(공용 언어 런타임) 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="be95d-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="be95d-104">구문</span><span class="sxs-lookup"><span data-stu-id="be95d-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="be95d-105">멤버</span><span class="sxs-lookup"><span data-stu-id="be95d-105">Members</span></span>  
  
|<span data-ttu-id="be95d-106">멤버</span><span class="sxs-lookup"><span data-stu-id="be95d-106">Member</span></span>|<span data-ttu-id="be95d-107">설명</span><span class="sxs-lookup"><span data-stu-id="be95d-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="be95d-108">대상 컴퓨터에서 실행되는 원격 디버깅 프록시에 의해 할당된 런타임 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="be95d-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="be95d-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="be95d-109">Requirements</span></span>  
 <span data-ttu-id="be95d-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="be95d-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="be95d-111">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="be95d-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="be95d-112">**라이브러리:** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="be95d-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="be95d-113">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="be95d-113">**.NET Framework Versions:** 3.5 SP1</span></span>
