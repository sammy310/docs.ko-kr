---
description: '다음에 대 한 자세한 정보: USER_THREAD 구조체'
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
ms.openlocfilehash: a4bd22073b7610307e67107781bdb68a15ef795f
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99761270"
---
# <a name="user_thread-structure"></a><span data-ttu-id="c73f3-103">USER_THREAD 구조체</span><span class="sxs-lookup"><span data-stu-id="c73f3-103">USER_THREAD Structure</span></span>

<span data-ttu-id="c73f3-104">스레드에 대 한 정보를 디버거에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="c73f3-104">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="c73f3-105">자세한 내용은 [INotifySource2:: SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="c73f3-105">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="c73f3-106">구문</span><span class="sxs-lookup"><span data-stu-id="c73f3-106">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="c73f3-107">구성원</span><span class="sxs-lookup"><span data-stu-id="c73f3-107">Members</span></span>  
  
|<span data-ttu-id="c73f3-108">멤버</span><span class="sxs-lookup"><span data-stu-id="c73f3-108">Member</span></span>|<span data-ttu-id="c73f3-109">설명</span><span class="sxs-lookup"><span data-stu-id="c73f3-109">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="c73f3-110">스레드 버퍼의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="c73f3-110">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="c73f3-111">스레드 버퍼의 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="c73f3-111">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="c73f3-112">스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="c73f3-112">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="c73f3-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="c73f3-113">Requirements</span></span>  

 <span data-ttu-id="c73f3-114">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="c73f3-114">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c73f3-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c73f3-115">See also</span></span>

- [<span data-ttu-id="c73f3-116">SetNotifyFilter 메서드</span><span class="sxs-lookup"><span data-stu-id="c73f3-116">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="c73f3-117">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="c73f3-117">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
