---
title: ICorDebugModule::GetToken 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
ms.openlocfilehash: 683c2853ea2ed43e61eb666ec56619cb58cde273
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73129491"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="94091-102">ICorDebugModule::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="94091-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="94091-103">이 모듈의 테이블 항목에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="94091-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="94091-104">구문</span><span class="sxs-lookup"><span data-stu-id="94091-104">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="94091-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="94091-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="94091-106">제한이 모듈의 메타 데이터를 참조 하는 `mdModule` 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="94091-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="94091-107">주의</span><span class="sxs-lookup"><span data-stu-id="94091-107">Remarks</span></span>  
 <span data-ttu-id="94091-108">토큰은 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md)및 [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata 가져오기 인터페이스에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94091-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="94091-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="94091-109">Requirements</span></span>  
 <span data-ttu-id="94091-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="94091-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="94091-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="94091-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="94091-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="94091-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="94091-113">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="94091-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="94091-114">참조</span><span class="sxs-lookup"><span data-stu-id="94091-114">See also</span></span>

- [<span data-ttu-id="94091-115">메타데이터</span><span class="sxs-lookup"><span data-stu-id="94091-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
