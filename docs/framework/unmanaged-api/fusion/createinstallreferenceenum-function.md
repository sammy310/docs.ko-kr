---
title: CreateInstallReferenceEnum 함수
ms.date: 03/30/2017
api_name:
- CreateInstallReferenceEnum
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateInstallReference
helpviewer_keywords:
- CreateInstallReference function [.NET Framework fusion]
ms.assetid: 80dbbbf8-54fc-4894-b74a-0179d3201083
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: d7820b33dcfacae5ede5235607e40d95940fc474
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59092827"
---
# <a name="createinstallreferenceenum-function"></a><span data-ttu-id="8b126-102">CreateInstallReferenceEnum 함수</span><span class="sxs-lookup"><span data-stu-id="8b126-102">CreateInstallReferenceEnum Function</span></span>
<span data-ttu-id="8b126-103">포인터를 가져는 [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) 인스턴스는 지정된 된 어셈블리에 대 한 응용 프로그램의 참조 목록을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8b126-103">Gets a pointer to an [IInstallReferenceEnum](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md) instance that represents a list of an application's references to the specified assembly.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8b126-104">구문</span><span class="sxs-lookup"><span data-stu-id="8b126-104">Syntax</span></span>  
  
```  
HRESULT CreateInstallReferenceEnum (  
    [out] IInstallReferenceEnum **ppRefEnum,  
    [in]  IAssemblyName         *pName,  
    [in]  DWORD                 dwFlags,  
    [in]  LPVOID                pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="8b126-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8b126-105">Parameters</span></span>  
 `ppRefEnum`  
 <span data-ttu-id="8b126-106">[out] 반환 된 `IInstallReferenceEnum` 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8b126-106">[out] The returned `IInstallReferenceEnum` pointer.</span></span>  
  
 `pName`  
 <span data-ttu-id="8b126-107">[in] 합니다 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 참조를 열거 하는 어셈블리를 식별 하는 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b126-107">[in] The [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) that identifies the assembly for which to enumerate references.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="8b126-108">[in] 열거자의 동작에 영향을 주는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="8b126-108">[in] Flags that influence the enumerator's behavior.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="8b126-109">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8b126-109">[in] Reserved for future extensibility.</span></span> `pvReserved` <span data-ttu-id="8b126-110">null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b126-110">must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8b126-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8b126-111">Requirements</span></span>  
 <span data-ttu-id="8b126-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b126-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8b126-113">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="8b126-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="8b126-114">**라이브러리:** Fusion.dll 및 Mscorwks.dll 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b126-114">**Library:** Fusion.dll and Mscorwks.dll.</span></span> <span data-ttu-id="8b126-115">올바른 버전의.NET Framework 대상 지정 하는 데 Mscorwks.dll 대신 Fusion.dll를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b126-115">Use Fusion.dll instead of Mscorwks.dll to ensure that you target the correct version of the .NET Framework.</span></span>  
  
 **<span data-ttu-id="8b126-116">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="8b126-116">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="8b126-117">참고자료</span><span class="sxs-lookup"><span data-stu-id="8b126-117">See also</span></span>

- [<span data-ttu-id="8b126-118">IInstallReferenceEnum 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b126-118">IInstallReferenceEnum Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iinstallreferenceenum-interface.md)
- [<span data-ttu-id="8b126-119">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8b126-119">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="8b126-120">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="8b126-120">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
