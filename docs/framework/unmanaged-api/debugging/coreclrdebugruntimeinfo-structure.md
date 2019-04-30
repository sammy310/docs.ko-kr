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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 88fcc5959054f1cdf7c9543674584a4bde26d896
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61966044"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="7ebe5-102">CoreClrDebugRuntimeInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="7ebe5-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="7ebe5-103">원격 컴퓨터의 프로세스에서 로드된 CLR(공용 언어 런타임) 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7ebe5-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="7ebe5-104">구문</span><span class="sxs-lookup"><span data-stu-id="7ebe5-104">Syntax</span></span>  
  
```  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="7ebe5-105">멤버</span><span class="sxs-lookup"><span data-stu-id="7ebe5-105">Members</span></span>  
  
|<span data-ttu-id="7ebe5-106">멤버</span><span class="sxs-lookup"><span data-stu-id="7ebe5-106">Member</span></span>|<span data-ttu-id="7ebe5-107">설명</span><span class="sxs-lookup"><span data-stu-id="7ebe5-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="7ebe5-108">대상 컴퓨터에서 실행되는 원격 디버깅 프록시에 의해 할당된 런타임 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="7ebe5-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="7ebe5-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7ebe5-109">Requirements</span></span>  
 <span data-ttu-id="7ebe5-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ebe5-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="7ebe5-111">**헤더:** CoreClrRemoteDebuggingInterfaces.h</span><span class="sxs-lookup"><span data-stu-id="7ebe5-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="7ebe5-112">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="7ebe5-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="7ebe5-113">**.NET framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="7ebe5-113">**.NET Framework Versions:** 3.5 SP1</span></span>
