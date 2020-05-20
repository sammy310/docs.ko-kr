---
title: USER_THREAD 구조체
ms.date: 03/30/2017
api_name:
- USER_THREAD
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- USER_THREAD
helpviewer_keywords:
- USER_THREAD structure [.NET Framework debugging]
ms.assetid: a57c7d71-c4b0-41f9-a964-0c5ee84a3124
topic_type:
- apiref
ms.openlocfilehash: 5144feab742bc5dac36563d701d81a699d0bb2f3
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83609445"
---
# <a name="user_thread-structure"></a><span data-ttu-id="bd462-102">USER_THREAD 구조체</span><span class="sxs-lookup"><span data-stu-id="bd462-102">USER_THREAD Structure</span></span>
<span data-ttu-id="bd462-103">스레드에 대 한 정보를 디버거에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="bd462-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="bd462-104">자세한 내용은 [INotifySource2:: SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="bd462-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="bd462-105">구문</span><span class="sxs-lookup"><span data-stu-id="bd462-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="bd462-106">멤버</span><span class="sxs-lookup"><span data-stu-id="bd462-106">Members</span></span>  
  
|<span data-ttu-id="bd462-107">멤버</span><span class="sxs-lookup"><span data-stu-id="bd462-107">Member</span></span>|<span data-ttu-id="bd462-108">설명</span><span class="sxs-lookup"><span data-stu-id="bd462-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="bd462-109">스레드 버퍼의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="bd462-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="bd462-110">스레드 버퍼의 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="bd462-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="bd462-111">스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="bd462-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="bd462-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="bd462-112">Requirements</span></span>  
 <span data-ttu-id="bd462-113">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="bd462-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="bd462-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="bd462-114">See also</span></span>

- [<span data-ttu-id="bd462-115">SetNotifyFilter 메서드</span><span class="sxs-lookup"><span data-stu-id="bd462-115">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="bd462-116">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="bd462-116">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
