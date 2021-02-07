---
description: '자세히 알아보기: CoreClrDebugRuntimeInfo Structure'
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
ms.openlocfilehash: 588e8bd1598996d1676e2df5517bd9a52eb59df4
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99661716"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="b2c6a-103">CoreClrDebugRuntimeInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="b2c6a-103">CoreClrDebugRuntimeInfo Structure</span></span>

<span data-ttu-id="b2c6a-104">원격 컴퓨터의 프로세스에서 로드된 CLR(공용 언어 런타임) 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b2c6a-104">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="b2c6a-105">구문</span><span class="sxs-lookup"><span data-stu-id="b2c6a-105">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="b2c6a-106">구성원</span><span class="sxs-lookup"><span data-stu-id="b2c6a-106">Members</span></span>  
  
|<span data-ttu-id="b2c6a-107">멤버</span><span class="sxs-lookup"><span data-stu-id="b2c6a-107">Member</span></span>|<span data-ttu-id="b2c6a-108">설명</span><span class="sxs-lookup"><span data-stu-id="b2c6a-108">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="b2c6a-109">대상 컴퓨터에서 실행되는 원격 디버깅 프록시에 의해 할당된 런타임 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="b2c6a-109">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="b2c6a-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="b2c6a-110">Requirements</span></span>  

 <span data-ttu-id="b2c6a-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="b2c6a-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="b2c6a-112">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="b2c6a-112">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="b2c6a-113">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="b2c6a-113">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="b2c6a-114">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="b2c6a-114">**.NET Framework Versions:** 3.5 SP1</span></span>
