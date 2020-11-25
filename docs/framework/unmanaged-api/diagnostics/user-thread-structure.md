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
ms.openlocfilehash: 409651aa69e957418ad46f61e1bd57add0eb10a6
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95722897"
---
# <a name="user_thread-structure"></a><span data-ttu-id="752f7-102">USER_THREAD 구조체</span><span class="sxs-lookup"><span data-stu-id="752f7-102">USER_THREAD Structure</span></span>

<span data-ttu-id="752f7-103">스레드에 대 한 정보를 디버거에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="752f7-103">Provides information to a debugger about a thread.</span></span> <span data-ttu-id="752f7-104">자세한 내용은 [INotifySource2:: SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) 메서드를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="752f7-104">For more information, see the [INotifySource2::SetNotifyFilter](inotifysource2-setnotifyfilter-method.md) method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="752f7-105">구문</span><span class="sxs-lookup"><span data-stu-id="752f7-105">Syntax</span></span>  
  
```cpp  
typedef struct tagUSER_THREAD  
{  
    BYTE    *pSidBuffer;  
    DWORD   dwSidLen;  
    DWORD   dwTid;  
} USER_THREAD;  
```  
  
## <a name="members"></a><span data-ttu-id="752f7-106">멤버</span><span class="sxs-lookup"><span data-stu-id="752f7-106">Members</span></span>  
  
|<span data-ttu-id="752f7-107">멤버</span><span class="sxs-lookup"><span data-stu-id="752f7-107">Member</span></span>|<span data-ttu-id="752f7-108">설명</span><span class="sxs-lookup"><span data-stu-id="752f7-108">Description</span></span>|  
|------------|-----------------|  
|`pSidBuffer`|<span data-ttu-id="752f7-109">스레드 버퍼의 주소입니다.</span><span class="sxs-lookup"><span data-stu-id="752f7-109">Address of thread buffer.</span></span>|  
|`dwSidLen`|<span data-ttu-id="752f7-110">스레드 버퍼의 길이 (바이트)입니다.</span><span class="sxs-lookup"><span data-stu-id="752f7-110">Length of thread buffer, in bytes.</span></span>|  
|`dwTid`|<span data-ttu-id="752f7-111">스레드 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="752f7-111">Thread ID.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="752f7-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="752f7-112">Requirements</span></span>  

 <span data-ttu-id="752f7-113">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="752f7-113">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="752f7-114">참조</span><span class="sxs-lookup"><span data-stu-id="752f7-114">See also</span></span>

- [<span data-ttu-id="752f7-115">SetNotifyFilter 메서드</span><span class="sxs-lookup"><span data-stu-id="752f7-115">SetNotifyFilter Method</span></span>](inotifysource2-setnotifyfilter-method.md)
- [<span data-ttu-id="752f7-116">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="752f7-116">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
