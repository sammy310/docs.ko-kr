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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: c28182feff8e4b7d49b7d068da1496d44fa2f917
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59150360"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="e72bb-102">ICorDebugModule::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="e72bb-102">ICorDebugModule::GetToken Method</span></span>
<span data-ttu-id="e72bb-103">이 모듈에 대 한 테이블 항목에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e72bb-103">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e72bb-104">구문</span><span class="sxs-lookup"><span data-stu-id="e72bb-104">Syntax</span></span>  
  
```  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="e72bb-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="e72bb-105">Parameters</span></span>  
 `pToken`  
 <span data-ttu-id="e72bb-106">[out] 에 대 한 포인터를 `mdModule` 모듈의 메타 데이터를 참조 하는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="e72bb-106">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="e72bb-107">설명</span><span class="sxs-lookup"><span data-stu-id="e72bb-107">Remarks</span></span>  
 <span data-ttu-id="e72bb-108">토큰을 전달할 수는 [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md)를 [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), 및 [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) 메타 데이터 가져오기 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="e72bb-108">The token can be passed to the [IMetaDataImport](../../../../docs/framework/unmanaged-api/metadata/imetadataimport-interface.md), [IMetaDataImport2](../../../../docs/framework/unmanaged-api/metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../../../../docs/framework/unmanaged-api/metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="e72bb-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="e72bb-109">Requirements</span></span>  
 <span data-ttu-id="e72bb-110">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="e72bb-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="e72bb-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="e72bb-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="e72bb-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="e72bb-112">**Library:** CorGuids.lib</span></span>  
  
 **<span data-ttu-id="e72bb-113">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="e72bb-113">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="e72bb-114">참고자료</span><span class="sxs-lookup"><span data-stu-id="e72bb-114">See also</span></span>

- [<span data-ttu-id="e72bb-115">메타데이터</span><span class="sxs-lookup"><span data-stu-id="e72bb-115">Metadata</span></span>](../../../../docs/framework/unmanaged-api/metadata/index.md)
