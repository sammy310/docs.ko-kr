---
description: '자세히 알아보기: CoreClrDebugProcInfo Structure'
title: CoreClrDebugProcInfo 구조체
ms.date: 03/30/2017
api_name:
- CoreClrDebugProcInfo
api_location:
- mscordbi_macx86.dll
api_type:
- COM
f1_keywords:
- CoreClrDebugProcInfo
helpviewer_keywords:
- remote debugging API [Silverlight]
- CoreClrDebugProcInfo structure
- Silverlight, remote debugging
ms.assetid: 4ddc37da-5c94-4beb-b61c-b54071c0e749
topic_type:
- apiref
ms.openlocfilehash: 04befb057be689e68dd3571a13990da9af64551f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99801490"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="70bda-103">CoreClrDebugProcInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="70bda-103">CoreClrDebugProcInfo Structure</span></span>

<span data-ttu-id="70bda-104">원격 컴퓨터에서 실행되는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="70bda-104">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="70bda-105">구문</span><span class="sxs-lookup"><span data-stu-id="70bda-105">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="70bda-106">구성원</span><span class="sxs-lookup"><span data-stu-id="70bda-106">Members</span></span>  
  
|<span data-ttu-id="70bda-107">멤버</span><span class="sxs-lookup"><span data-stu-id="70bda-107">Member</span></span>|<span data-ttu-id="70bda-108">설명</span><span class="sxs-lookup"><span data-stu-id="70bda-108">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="70bda-109">OS에서 할당한 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="70bda-109">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="70bda-110">대상 컴퓨터에서 실행되는 원격 디버깅 프록시에 의해 할당된 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="70bda-110">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="70bda-111">이 식별자는 OS 식별자만큼 자주 재활용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="70bda-111">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="70bda-112">프로세스의 명령줄입니다.</span><span class="sxs-lookup"><span data-stu-id="70bda-112">Command-line of the process.</span></span> <span data-ttu-id="70bda-113">이 멤버는 잘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="70bda-113">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="70bda-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="70bda-114">Requirements</span></span>  

 <span data-ttu-id="70bda-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="70bda-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="70bda-116">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="70bda-116">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="70bda-117">**라이브러리:** mscordbi_macx86.dll</span><span class="sxs-lookup"><span data-stu-id="70bda-117">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="70bda-118">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="70bda-118">**.NET Framework Versions:** 3.5 SP1</span></span>
