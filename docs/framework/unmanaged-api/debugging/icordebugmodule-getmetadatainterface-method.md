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
ms.openlocfilehash: fb96949e22b4edfc0e64780a54bb38da44eb8369
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129544"
---
# <a name="icordebugmodulegetmetadatainterface-method"></a><span data-ttu-id="5b305-102">ICorDebugModule::GetMetaDataInterface 메서드</span><span class="sxs-lookup"><span data-stu-id="5b305-102">ICorDebugModule::GetMetaDataInterface Method</span></span>
<span data-ttu-id="5b305-103">모듈에 대 한 메타 데이터를 검사 하는 데 사용할 수 있는 메타 데이터 인터페이스 개체를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="5b305-103">Gets a metadata interface object that can be used to examine the metadata for the module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="5b305-104">구문</span><span class="sxs-lookup"><span data-stu-id="5b305-104">Syntax</span></span>  
  
```cpp  
HRESULT GetMetaDataInterface (  
    [in] REFIID      riid,  
    [out] IUnknown **ppObj  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="5b305-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="5b305-105">Parameters</span></span>  
 `riid`  
 <span data-ttu-id="5b305-106">진행 메타 데이터 인터페이스를 지정 하는 참조 ID입니다.</span><span class="sxs-lookup"><span data-stu-id="5b305-106">[in] The reference ID that specifies the metadata interface.</span></span>  
  
 `ppObj`  
 <span data-ttu-id="5b305-107">제한이 [메타 데이터 인터페이스](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)중 하나인 `T:IUnknown` 개체의 주소에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="5b305-107">[out] A pointer to the address of an `T:IUnknown` object that is one of the [metadata interfaces](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md).</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="5b305-108">주의</span><span class="sxs-lookup"><span data-stu-id="5b305-108">Remarks</span></span>  
 <span data-ttu-id="5b305-109">디버거는 `GetMetaDataInterface` 메서드를 사용 하 여 모듈에 대 한 원래 메타 데이터의 복사본을 만들 수 있습니다 .이 경우 해당 모듈을 편집 하기 위해이 작업을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b305-109">The debugger can use the `GetMetaDataInterface` method to make a copy of the original metadata for a module, which it must do in order to edit that module.</span></span> <span data-ttu-id="5b305-110">디버거는 `GetMetaDataInterface`를 호출 하 여 모듈에 대 한 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 인터페이스 개체를 가져온 다음 [IMetaDataEmit:: SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) 를 호출 하 여 모듈의 메타 데이터 복사본을 메모리에 저장 합니다.</span><span class="sxs-lookup"><span data-stu-id="5b305-110">The debugger calls `GetMetaDataInterface` to get an [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) interface object for the module, then calls [IMetaDataEmit::SaveToMemory](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-savetomemory-method.md) to save a copy of the module's metadata to memory.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="5b305-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="5b305-111">Requirements</span></span>  
 <span data-ttu-id="5b305-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b305-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="5b305-113">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="5b305-113">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="5b305-114">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="5b305-114">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="5b305-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="5b305-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="5b305-116">참조</span><span class="sxs-lookup"><span data-stu-id="5b305-116">See also</span></span>

- [<span data-ttu-id="5b305-117">메타데이터</span><span class="sxs-lookup"><span data-stu-id="5b305-117">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
