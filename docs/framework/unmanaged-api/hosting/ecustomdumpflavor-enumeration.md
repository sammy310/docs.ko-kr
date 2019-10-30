---
title: ECustomDumpFlavor 열거형
ms.date: 03/30/2017
api_name:
- ECustomDumpFlavor
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ECustomDumpFlavor
helpviewer_keywords:
- ECustomDumpFlavor enumeration [.NET Framework hosting]
ms.assetid: b39b3320-fac7-41f1-9a03-ab6fb0cd89c7
topic_type:
- apiref
ms.openlocfilehash: 057794fe524a0ee01f6f090ca7e11a4a4b523047
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73124922"
---
# <a name="ecustomdumpflavor-enumeration"></a><span data-ttu-id="6933a-102">ECustomDumpFlavor 열거형</span><span class="sxs-lookup"><span data-stu-id="6933a-102">ECustomDumpFlavor Enumeration</span></span>
<span data-ttu-id="6933a-103">오류를 보고할 때 힙 덤프의 사용자 지정 하위 집합에 포함할 항목을 나타내는 값을 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="6933a-103">Contains values that indicate which items to include in a custom subset of a heap dump when reporting errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6933a-104">구문</span><span class="sxs-lookup"><span data-stu-id="6933a-104">Syntax</span></span>  
  
```cpp  
typedef enum {  
    DUMP_FLAVOR_Mini            = 1,  
    DUMP_FLAVOR_NonHeapCLRState = 2  
} ECustomDumpFlavor;  
```  
  
## <a name="members"></a><span data-ttu-id="6933a-105">멤버</span><span class="sxs-lookup"><span data-stu-id="6933a-105">Members</span></span>  
  
|<span data-ttu-id="6933a-106">멤버</span><span class="sxs-lookup"><span data-stu-id="6933a-106">Member</span></span>|<span data-ttu-id="6933a-107">설명</span><span class="sxs-lookup"><span data-stu-id="6933a-107">Description</span></span>|  
|------------|-----------------|  
|`DUMP_FLAVOR_Mini`|<span data-ttu-id="6933a-108">사용자 지정 힙 덤프가 미니 덤프로 시작 되 고 동일한 메서드에 전달 된 [Custom덤프 항목](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) 인스턴스에 의해 지정 된 추가 데이터를 포함 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6933a-108">Specifies that the custom heap dump should start as a minidump and include extra data specified by any [CustomDumpItem](../../../../docs/framework/unmanaged-api/hosting/customdumpitem-structure.md) instances passed to the same method.</span></span>|  
|`DUMP_FLAVOR_NonHeapCLRState`|<span data-ttu-id="6933a-109">사용자 지정 힙 덤프가 동적으로 할당 되지 않은 모든 런타임 상태 데이터를 수집 하도록 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="6933a-109">Specifies that the custom heap dump should gather all run-time state data that was not dynamically allocated.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="6933a-110">주의</span><span class="sxs-lookup"><span data-stu-id="6933a-110">Remarks</span></span>  
 <span data-ttu-id="6933a-111">`ECustomDumpFlavor` 형식의 매개 변수는 [ICLRErrorReportingManager:: BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) 메서드에 전달 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6933a-111">A parameter of type `ECustomDumpFlavor` is passed to the [ICLRErrorReportingManager::BeginCustomDump](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-begincustomdump-method.md) method.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6933a-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6933a-112">Requirements</span></span>  
 <span data-ttu-id="6933a-113">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6933a-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6933a-114">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6933a-114">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="6933a-115">**라이브러리:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="6933a-115">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="6933a-116">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6933a-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6933a-117">참조</span><span class="sxs-lookup"><span data-stu-id="6933a-117">See also</span></span>

- [<span data-ttu-id="6933a-118">ECustomDumpItemKind 열거형</span><span class="sxs-lookup"><span data-stu-id="6933a-118">ECustomDumpItemKind Enumeration</span></span>](../../../../docs/framework/unmanaged-api/hosting/ecustomdumpitemkind-enumeration.md)
- [<span data-ttu-id="6933a-119">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6933a-119">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="6933a-120">호스팅 열거형</span><span class="sxs-lookup"><span data-stu-id="6933a-120">Hosting Enumerations</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-enumerations.md)
