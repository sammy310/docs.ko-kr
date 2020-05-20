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
ms.openlocfilehash: e8dda83df8a320733f45dbcc13599cdf37d26492
ms.sourcegitcommit: 27db07ffb26f76912feefba7b884313547410db5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2020
ms.locfileid: "83617154"
---
# <a name="host_type-enumeration"></a><span data-ttu-id="987b8-102">HOST_TYPE 열거형</span><span class="sxs-lookup"><span data-stu-id="987b8-102">HOST_TYPE Enumeration</span></span>
<span data-ttu-id="987b8-103">응용 프로그램을 시작 하는 호스트의 유형을 지정 하는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="987b8-103">Contains values that specify the type of host that is launching an application.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="987b8-104">구문</span><span class="sxs-lookup"><span data-stu-id="987b8-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    HOST_TYPE_DEFAULT     = 0x0,  
    HOST_TYPE_APPLAUNCH   = 0x1,  
    HOST_TYPE_CORFLAG     = 0x2  
} HOST_TYPE;  
```  
  
## <a name="members"></a><span data-ttu-id="987b8-105">멤버</span><span class="sxs-lookup"><span data-stu-id="987b8-105">Members</span></span>  
  
|<span data-ttu-id="987b8-106">멤버</span><span class="sxs-lookup"><span data-stu-id="987b8-106">Member</span></span>|<span data-ttu-id="987b8-107">설명</span><span class="sxs-lookup"><span data-stu-id="987b8-107">Description</span></span>|  
|------------|-----------------|  
|`HOST_TYPE_APPLAUNCH`|<span data-ttu-id="987b8-108">AppLaunch에서 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="987b8-108">Launch the application from AppLaunch.exe.</span></span><br /><br /> <span data-ttu-id="987b8-109">부분적으로 신뢰할 수 있는 응용 프로그램에이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="987b8-109">Use this value for partially-trusted applications.</span></span>|  
|`HOST_TYPE_CORFLAG`|<span data-ttu-id="987b8-110">응용 프로그램을 직접 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="987b8-110">Launch the application directly.</span></span> <span data-ttu-id="987b8-111">즉, 자체 .exe 파일에서 응용 프로그램을 시작 합니다.</span><span class="sxs-lookup"><span data-stu-id="987b8-111">That is, launch the application from its own .exe file.</span></span><br /><br /> <span data-ttu-id="987b8-112">완전히 신뢰할 수 있는 응용 프로그램에이 값을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="987b8-112">Use this value for fully-trusted applications.</span></span>|  
|`HOST_TYPE_DEFAULT`|<span data-ttu-id="987b8-113">HOST_TYPE_APPLAUNCH와 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="987b8-113">Same as HOST_TYPE_APPLAUNCH.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="987b8-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="987b8-114">Requirements</span></span>  
 <span data-ttu-id="987b8-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="987b8-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="987b8-116">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="987b8-116">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="987b8-117">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="987b8-117">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="987b8-118">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="987b8-118">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="987b8-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="987b8-119">See also</span></span>

- [<span data-ttu-id="987b8-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="987b8-120">Hosting Enumerations</span></span>](hosting-enumerations.md)
