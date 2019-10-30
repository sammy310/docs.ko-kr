---
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
ms.openlocfilehash: e12882e53d1aa2120ab5c4b6793d7f2e34be76eb
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73132160"
---
# <a name="coreclrdebugprocinfo-structure"></a><span data-ttu-id="63d27-102">CoreClrDebugProcInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="63d27-102">CoreClrDebugProcInfo Structure</span></span>
<span data-ttu-id="63d27-103">원격 컴퓨터에서 실행되는 프로세스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="63d27-103">Represents a process that is running on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="63d27-104">구문</span><span class="sxs-lookup"><span data-stu-id="63d27-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugProcInfo {  
    DWORD m_dwPID;  
    DWORD m_dwInternalID;  
    WCHAR m_wszName[256];  
};  
```  
  
## <a name="members"></a><span data-ttu-id="63d27-105">멤버</span><span class="sxs-lookup"><span data-stu-id="63d27-105">Members</span></span>  
  
|<span data-ttu-id="63d27-106">멤버</span><span class="sxs-lookup"><span data-stu-id="63d27-106">Member</span></span>|<span data-ttu-id="63d27-107">설명</span><span class="sxs-lookup"><span data-stu-id="63d27-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwPID`|<span data-ttu-id="63d27-108">OS에서 할당한 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="63d27-108">OS-assigned process identifier.</span></span>|  
|`m_dwInternalID`|<span data-ttu-id="63d27-109">대상 컴퓨터에서 실행되는 원격 디버깅 프록시에 의해 할당된 프로세스 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="63d27-109">Process identifier that is assigned by the remote debugging proxy running on the target machine.</span></span> <span data-ttu-id="63d27-110">이 식별자는 OS 식별자만큼 자주 재활용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="63d27-110">This identifier recycles less often than the OS identifier.</span></span>|  
|`m_wszName`|<span data-ttu-id="63d27-111">프로세스의 명령줄입니다.</span><span class="sxs-lookup"><span data-stu-id="63d27-111">Command-line of the process.</span></span> <span data-ttu-id="63d27-112">이 멤버는 잘릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="63d27-112">This member may be truncated.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="63d27-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="63d27-113">Requirements</span></span>  
 <span data-ttu-id="63d27-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="63d27-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="63d27-115">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="63d27-115">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="63d27-116">**라이브러리:** mscordbi_macx86</span><span class="sxs-lookup"><span data-stu-id="63d27-116">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="63d27-117">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="63d27-117">**.NET Framework Versions:** 3.5 SP1</span></span>
