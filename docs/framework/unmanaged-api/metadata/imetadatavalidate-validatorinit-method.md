---
title: IMetaDataValidate::ValidatorInit 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataValidate.ValidatorInit
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate::ValidatorInit
helpviewer_keywords:
- IMetaDataValidate::ValidatorInit method [.NET Framework metadata]
- ValidatorInit method [.NET Framework metadata]
ms.assetid: 6bafd75a-e2d0-4aea-aed1-074374d5dff6
topic_type:
- apiref
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 31ff2c62810061cd8b774e934167a5ee3acf040c
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59195894"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="d5efa-102">IMetaDataValidate::ValidatorInit 메서드</span><span class="sxs-lookup"><span data-stu-id="d5efa-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="d5efa-103">현재 메타데이터 범위에서 모듈 형식을 지정하는 플래그를 설정하고 유효성 검사 오류에 대한 지정된 콜백 메서드를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="d5efa-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d5efa-104">구문</span><span class="sxs-lookup"><span data-stu-id="d5efa-104">Syntax</span></span>  
  
```  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="d5efa-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="d5efa-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="d5efa-106">[in] 값을 [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) 현재 메타 데이터 범위에서 모듈의 형식을 지정 하는 열거형입니다.</span><span class="sxs-lookup"><span data-stu-id="d5efa-106">[in] A value of the [CorValidatorModuleType](../../../../docs/framework/unmanaged-api/metadata/corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="d5efa-107">[in] 에 대 한 포인터를 [IUnknown](/cpp/atl/iunknown) 유효성 검사 오류에 대 한 함수 콜백으로 사용 되는 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="d5efa-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="d5efa-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d5efa-108">Requirements</span></span>  
 <span data-ttu-id="d5efa-109">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="d5efa-109">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="d5efa-110">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="d5efa-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="d5efa-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="d5efa-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="d5efa-112">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="d5efa-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d5efa-113">참고자료</span><span class="sxs-lookup"><span data-stu-id="d5efa-113">See also</span></span>

- [<span data-ttu-id="d5efa-114">IMetaDataValidate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="d5efa-114">IMetaDataValidate Interface</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-interface.md)
