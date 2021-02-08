---
description: '다음에 대 한 자세한 정보: 열거형 HOST_TYPE'
title: HOST_TYPE 열거형
ms.date: 03/30/2017
api_name:
- HOST_TYPE
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- HOST_TYPE
helpviewer_keywords:
- HOST_TYPE enumeration [.NET Framework hosting]
ms.assetid: 51f848be-84c5-4036-9839-c762c576bbf5
topic_type:
- apiref
ms.openlocfilehash: 6a0baf3050f99885953ddec06342cbe19accfef3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99785239"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="805c6-103">HOST_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="805c6-103">HOST_TYPE Enumeration</span></span>

<span data-ttu-id="805c6-104">응용 프로그램을 시작 하는 호스트의 유형을 지정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="805c6-104">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="805c6-105">구문</span><span class="sxs-lookup"><span data-stu-id="805c6-105">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="805c6-106">구성원</span><span class="sxs-lookup"><span data-stu-id="805c6-106">Members</span></span>  
  
|<span data-ttu-id="805c6-107">멤버</span><span class="sxs-lookup"><span data-stu-id="805c6-107">Member</span></span>|<span data-ttu-id="805c6-108">설명</span><span class="sxs-lookup"><span data-stu-id="805c6-108">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="805c6-109">AppLaunch.exe에서 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="805c6-109">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="805c6-110">부분적으로 신뢰할 수 있는 응용 프로그램에이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="805c6-110">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="805c6-111">응용 프로그램을 직접 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="805c6-111">Launch the application directly.</span></span> <span data-ttu-id="805c6-112">즉, 자체 .exe 파일에서 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="805c6-112">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="805c6-113">완전히 신뢰할 수 있는 응용 프로그램에이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="805c6-113">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="805c6-114">HOST_TYPE_APPLAUNCH와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="805c6-114">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="805c6-115">요구 사항</span><span class="sxs-lookup"><span data-stu-id="805c6-115">Requirements</span></span>  

 <span data-ttu-id="805c6-116">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="805c6-116">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="805c6-117">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="805c6-117">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="805c6-118">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="805c6-118">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="805c6-119">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="805c6-119">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="805c6-120">참고 항목</span><span class="sxs-lookup"><span data-stu-id="805c6-120">See also</span></span>

- [<span data-ttu-id="805c6-121">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="805c6-121">Hosting Enumerations</span></span>](hosting-enumerations.md)
