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
ms.openlocfilehash: 2c41e7db32ee8557a6c03217b95fd5b040655c70
ms.sourcegitcommit: d9c7ac5d06735a01c1fafe34efe9486734841a72
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2020
ms.locfileid: "82860933"
---
# <a name="coreclrdebugruntimeinfo-structure"></a><span data-ttu-id="8504c-102">CoreClrDebugRuntimeInfo 구조체</span><span class="sxs-lookup"><span data-stu-id="8504c-102">CoreClrDebugRuntimeInfo Structure</span></span>
<span data-ttu-id="8504c-103">원격 컴퓨터의 프로세스에서 로드된 CLR(공용 언어 런타임) 인스턴스를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8504c-103">Represents a common language runtime (CLR) instance that is loaded in a process on a remote machine.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8504c-104">구문</span><span class="sxs-lookup"><span data-stu-id="8504c-104">Syntax</span></span>  
  
```cpp  
struct  CoreClrDebugRuntimeInfo {  
    DWORD m_dwInternalID;  
};  
```  
  
## <a name="members"></a><span data-ttu-id="8504c-105">구성원</span><span class="sxs-lookup"><span data-stu-id="8504c-105">Members</span></span>  
  
|<span data-ttu-id="8504c-106">멤버</span><span class="sxs-lookup"><span data-stu-id="8504c-106">Member</span></span>|<span data-ttu-id="8504c-107">Description</span><span class="sxs-lookup"><span data-stu-id="8504c-107">Description</span></span>|  
|------------|-----------------|  
|`m_dwInternalID`|<span data-ttu-id="8504c-108">대상 컴퓨터에서 실행되는 원격 디버깅 프록시에 의해 할당된 런타임 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="8504c-108">Runtime identifier that is assigned by the remote debugging proxy running on the target machine.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8504c-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8504c-109">Requirements</span></span>  
 <span data-ttu-id="8504c-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8504c-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8504c-111">**헤더:** CoreClrRemoteDebuggingInterfaces</span><span class="sxs-lookup"><span data-stu-id="8504c-111">**Header:** CoreClrRemoteDebuggingInterfaces.h</span></span>  
  
 <span data-ttu-id="8504c-112">**라이브러리:** mscordbi_macx86 .dll</span><span class="sxs-lookup"><span data-stu-id="8504c-112">**Library:** mscordbi_macx86.dll</span></span>  
  
 <span data-ttu-id="8504c-113">**.NET Framework 버전:** 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="8504c-113">**.NET Framework Versions:** 3.5 SP1</span></span>
