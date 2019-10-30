---
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
ms.openlocfilehash: cc0cea10b4a209583fb7afb551a6b80d52ad7f62
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73127024"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="fbf7e-102">HOST_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="fbf7e-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="fbf7e-103">응용 프로그램을 시작 하는 호스트의 유형을 지정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf7e-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fbf7e-104">구문</span><span class="sxs-lookup"><span data-stu-id="fbf7e-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="fbf7e-105">멤버</span><span class="sxs-lookup"><span data-stu-id="fbf7e-105">Members</span></span>  
  
|<span data-ttu-id="fbf7e-106">멤버</span><span class="sxs-lookup"><span data-stu-id="fbf7e-106">Member</span></span>|<span data-ttu-id="fbf7e-107">설명</span><span class="sxs-lookup"><span data-stu-id="fbf7e-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="fbf7e-108">AppLaunch에서 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf7e-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="fbf7e-109">부분적으로 신뢰할 수 있는 응용 프로그램에이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf7e-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="fbf7e-110">응용 프로그램을 직접 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf7e-110">Launch the application directly.</span></span> <span data-ttu-id="fbf7e-111">즉, 자체 .exe 파일에서 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf7e-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="fbf7e-112">완전히 신뢰할 수 있는 응용 프로그램에이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf7e-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="fbf7e-113">HOST_TYPE_APPLAUNCH와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="fbf7e-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fbf7e-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fbf7e-114">Requirements</span></span>  
 <span data-ttu-id="fbf7e-115">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fbf7e-115">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fbf7e-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fbf7e-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="fbf7e-117">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="fbf7e-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fbf7e-118">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fbf7e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fbf7e-119">참조</span><span class="sxs-lookup"><span data-stu-id="fbf7e-119">See also</span></span>

- [<span data-ttu-id="fbf7e-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="fbf7e-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
