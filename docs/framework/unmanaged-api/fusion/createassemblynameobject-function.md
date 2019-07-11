---
title: CreateAssemblyNameObject 함수
ms.date: 03/30/2017
api_name:
- CreateAssemblyNameObject
api_location:
- fusion.dll
- clr.dll
- mscorwks.dll
api_type:
- DLLExport
f1_keywords:
- CreateAssemblyNameObject
helpviewer_keywords:
- CreateAssemblyNameObject function [.NET Framework fusion]
ms.assetid: 55c8b41e-fbe4-4ae0-aa29-68fbb2311691
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: ed26df6580aeaf2936bd50c9f1855a08ac68b90b
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67778427"
---
# <a name="createassemblynameobject-function"></a><span data-ttu-id="de598-102">CreateAssemblyNameObject 함수</span><span class="sxs-lookup"><span data-stu-id="de598-102">CreateAssemblyNameObject Function</span></span>
<span data-ttu-id="de598-103">한 인터페이스 포인터를 가져옵니다는 [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) 지정한 이름 가진 어셈블리의 고유 id를 나타내는 인스턴스입니다.</span><span class="sxs-lookup"><span data-stu-id="de598-103">Gets an interface pointer to an [IAssemblyName](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md) instance that represents the unique identity of the assembly with the specified name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="de598-104">구문</span><span class="sxs-lookup"><span data-stu-id="de598-104">Syntax</span></span>  
  
```cpp  
HRESULT CreateAssemblyNameObject (  
    [out] LPASSEMBLYNAME  *ppAssemblyNameObj,  
    [in]  LPCWSTR         szAssemblyName,  
    [in]  DWORD           dwFlags,  
    [in]  LPVOID          pvReserved  
 );  
```  
  
## <a name="parameters"></a><span data-ttu-id="de598-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="de598-105">Parameters</span></span>  
 `ppAssemblyNameObj`  
 <span data-ttu-id="de598-106">[out] 반환 된 `IAssemblyName`합니다.</span><span class="sxs-lookup"><span data-stu-id="de598-106">[out] The returned `IAssemblyName`.</span></span>  
  
 `szAssemblyName`  
 <span data-ttu-id="de598-107">[in] 만들려는 새 어셈블리의 이름을 `IAssemblyName` 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="de598-107">[in] The name of the assembly for which to create the new `IAssemblyName` instance.</span></span>  
  
 `dwFlags`  
 <span data-ttu-id="de598-108">[in] 개체 생성자에 전달 하는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="de598-108">[in] Flags to pass to the object constructor.</span></span>  
  
 `pvReserved`  
 <span data-ttu-id="de598-109">[in] 향후 확장성을 위해 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="de598-109">[in] Reserved for future extensibility.</span></span> <span data-ttu-id="de598-110">`pvReserved` null 참조 여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="de598-110">`pvReserved` must be a null reference.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="de598-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="de598-111">Requirements</span></span>  
 <span data-ttu-id="de598-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="de598-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="de598-113">**헤더:** Fusion.h</span><span class="sxs-lookup"><span data-stu-id="de598-113">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="de598-114">**라이브러리:** MsCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="de598-114">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="de598-115">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="de598-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="de598-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="de598-116">See also</span></span>

- [<span data-ttu-id="de598-117">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="de598-117">IAssemblyName Interface</span></span>](../../../../docs/framework/unmanaged-api/fusion/iassemblyname-interface.md)
- [<span data-ttu-id="de598-118">Fusion 전역 정적 함수</span><span class="sxs-lookup"><span data-stu-id="de598-118">Fusion Global Static Functions</span></span>](../../../../docs/framework/unmanaged-api/fusion/fusion-global-static-functions.md)
