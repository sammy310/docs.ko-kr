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
ms.openlocfilehash: 687f33c364f9730a554a41ade1ca2b78e33ffdc5
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84489723"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="ca77c-102">IMetaDataValidate::ValidatorInit 메서드</span><span class="sxs-lookup"><span data-stu-id="ca77c-102">IMetaDataValidate::ValidatorInit Method</span></span>
<span data-ttu-id="ca77c-103">현재 메타데이터 범위에서 모듈 형식을 지정하는 플래그를 설정하고 유효성 검사 오류에 대한 지정된 콜백 메서드를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="ca77c-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ca77c-104">구문</span><span class="sxs-lookup"><span data-stu-id="ca77c-104">Syntax</span></span>  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ca77c-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ca77c-105">Parameters</span></span>  
 `dwModule`  
 <span data-ttu-id="ca77c-106">진행 현재 메타 데이터 범위에서 모듈의 유형을 지정 하는 [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="ca77c-106">[in] A value of the [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="ca77c-107">진행 유효성 검사 오류에 대 한 함수 콜백 역할을 하는 [IUnknown](/cpp/atl/iunknown) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="ca77c-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ca77c-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ca77c-108">Requirements</span></span>  
 <span data-ttu-id="ca77c-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ca77c-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ca77c-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="ca77c-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="ca77c-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="ca77c-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="ca77c-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ca77c-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ca77c-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="ca77c-113">See also</span></span>

- [<span data-ttu-id="ca77c-114">IMetaDataValidate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ca77c-114">IMetaDataValidate Interface</span></span>](imetadatavalidate-interface.md)
