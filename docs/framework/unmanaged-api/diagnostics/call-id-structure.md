---
title: CALL_ID 구조체
ms.date: 03/30/2017
api_name:
- CALL_ID
api_location:
- diasymreader.dll
api_type:
- COM
f1_keywords:
- CALL_ID
helpviewer_keywords:
- CALL_ID structure [.NET Framework debugging]
ms.assetid: bfd46324-afec-4782-9c18-586d81fb4740
topic_type:
- apiref
ms.openlocfilehash: 1c795ee536483a7def9c0339efae66a013898a77
ms.sourcegitcommit: 9a4488a3625866335e83a20da5e9c5286b1f034c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/15/2020
ms.locfileid: "83420632"
---
# <a name="call_id-structure"></a><span data-ttu-id="13ac8-102">CALL_ID 구조체</span><span class="sxs-lookup"><span data-stu-id="13ac8-102">CALL_ID Structure</span></span>
<span data-ttu-id="13ac8-103">호출 되는 함수에 대 한 정보를 디버거에 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac8-103">Provides information to a debugger about a function that is being called.</span></span> <span data-ttu-id="13ac8-104">자세한 내용은 [INotifySink2](inotifysink2-interface.md) 인터페이스를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="13ac8-104">See the [INotifySink2](inotifysink2-interface.md) interface for more information.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="13ac8-105">구문</span><span class="sxs-lookup"><span data-stu-id="13ac8-105">Syntax</span></span>  
  
```cpp  
typedef struct tagCALL_ID  
{  
    LPCOLESTR       szMachine;  
    DWORD           dwPid;  
    USER_THREAD     *pUserThread;  
    STACK_ADDRESS   addrStackPointer;  
    LPCOLESTR       szEntryPoint;  
    LPCOLESTR       szDestinationMachine;  
} CALL_ID;  
```  
  
## <a name="members"></a><span data-ttu-id="13ac8-106">멤버</span><span class="sxs-lookup"><span data-stu-id="13ac8-106">Members</span></span>  
  
|<span data-ttu-id="13ac8-107">멤버</span><span class="sxs-lookup"><span data-stu-id="13ac8-107">Member</span></span>|<span data-ttu-id="13ac8-108">설명</span><span class="sxs-lookup"><span data-stu-id="13ac8-108">Description</span></span>|  
|------------|-----------------|  
|`szMachine`|<span data-ttu-id="13ac8-109">호출을 수행 하는 컴퓨터를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac8-109">Identifies the machine that is making the call.</span></span>|  
|`dwPid`|<span data-ttu-id="13ac8-110">컴퓨터 프로세서를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac8-110">Identifies the machine processor.</span></span>|  
|`pUserThread`|<span data-ttu-id="13ac8-111">호출을 실행 하는 스레드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac8-111">Identifies the thread that is executing the call.</span></span>|  
|`addrStackPointer`|<span data-ttu-id="13ac8-112">호출 스택의 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac8-112">Specifies the address of the call stack.</span></span>|  
|`szEntryPoint`|<span data-ttu-id="13ac8-113">호출의 주소를 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac8-113">Specifies the address of the call.</span></span>|  
|`szDestinationMachine`|<span data-ttu-id="13ac8-114">호출을 실행할 컴퓨터를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="13ac8-114">Identifies the machine that will execute the call.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="13ac8-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="13ac8-115">Requirements</span></span>  
 <span data-ttu-id="13ac8-116">**헤더:** ProtocolNotify2</span><span class="sxs-lookup"><span data-stu-id="13ac8-116">**Header:** ProtocolNotify2.idl</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="13ac8-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="13ac8-117">See also</span></span>

- [<span data-ttu-id="13ac8-118">INotifySink2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="13ac8-118">INotifySink2 Interface</span></span>](inotifysink2-interface.md)
- [<span data-ttu-id="13ac8-119">진단 기호 저장소 구조체</span><span class="sxs-lookup"><span data-stu-id="13ac8-119">Diagnostics Symbol Store Structures</span></span>](diagnostics-symbol-store-structures.md)
