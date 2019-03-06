---
title: ICorDebugModule::GetMetaDataInterface 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetMetaDataInterface
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetMetaDataInterface
helpviewer_keywords:
- ICorDebugModule::GetMetaDatainterface method [.NET Framework debugging]
- GetMetaDatainterface method [.NET Framework debugging]
ms.assetid: 30d906f2-cf35-4fa9-9d4c-0c31b58c9f3a
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: e5d28118ea1cc26f80ecc67ccedd160447aa69a4
ms.sourcegitcommit: 5137208fa414d9ca3c58cdfd2155ac81bc89e917
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2019
ms.locfileid: "57479036"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="d5497-102">ICorDebugModule::GetMetaDataInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="d5497-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="d5497-103">모듈에 대 한 메타 데이터를 검사 하는 메타 데이터 인터페이스 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="d5497-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5497-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5497-104">Syntax</span></span>  
  
```  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5497-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5497-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="d5497-106">[in] 메타 데이터 인터페이스를 지정 하는 참조 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="d5497-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="d5497-107">[out] 주소에 대 한 포인터를 `T:IUnknown` 중 하나는 개체를 [메타 데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span><span class="sxs-lookup"><span data-stu-id="d5497-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="d5497-108">설명</span><span class="sxs-lookup"><span data-stu-id="d5497-108">Remarks</span></span>  
 <span data-ttu-id="d5497-109">디버거에서 사용할 수는 `GetMetaDataInterface` 메서드를 해당 모듈을 편집 하기 위해 수행 해야 하는 모듈에 대 한 원래 메타 데이터의 복사본을 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="d5497-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="d5497-110">디버거 호출 `GetMetaDataInterface` 가져오기에 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 인터페이스 개체 모듈에 대 한 호출 [imetadataemit:: Savetomemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) 메모리 모듈의 메타 데이터의 복사본을 저장 하려면.</span><span class="sxs-lookup"><span data-stu-id="d5497-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5497-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5497-111">Requirements</span></span>  
 <span data-ttu-id="d5497-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5497-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5497-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="d5497-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="d5497-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="d5497-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="d5497-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5497-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5497-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5497-116">See also</span></span>
- [<span data-ttu-id="d5497-117">메타데이터</span><span class="sxs-lookup"><span data-stu-id="d5497-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
