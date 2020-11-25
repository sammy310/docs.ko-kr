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
ms.openlocfilehash: e2f54e11906cd4ba1440e220530f2ca5b9de769f
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95708558"
---
# <a name="imetadatavalidatevalidatorinit-method"></a><span data-ttu-id="86fdf-102">IMetaDataValidate::ValidatorInit 메서드</span><span class="sxs-lookup"><span data-stu-id="86fdf-102">IMetaDataValidate::ValidatorInit Method</span></span>

<span data-ttu-id="86fdf-103">현재 메타데이터 범위에서 모듈 형식을 지정하는 플래그를 설정하고 유효성 검사 오류에 대한 지정된 콜백 메서드를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="86fdf-103">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="86fdf-104">구문</span><span class="sxs-lookup"><span data-stu-id="86fdf-104">Syntax</span></span>  
  
```cpp  
HRESULT ValidatorInit (  
   [in] DWORD       dwModuleType,  
   [in] IUnknown    *pUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="86fdf-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="86fdf-105">Parameters</span></span>  

 `dwModule`  
 <span data-ttu-id="86fdf-106">진행 현재 메타 데이터 범위에서 모듈의 유형을 지정 하는 [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) 열거형의 값입니다.</span><span class="sxs-lookup"><span data-stu-id="86fdf-106">[in] A value of the [CorValidatorModuleType](corvalidatormoduletype-enumeration.md) enumeration that specifies the type of the module in the current metadata scope.</span></span>  
  
 `pUnk`  
 <span data-ttu-id="86fdf-107">진행 유효성 검사 오류에 대 한 함수 콜백 역할을 하는 [IUnknown](/cpp/atl/iunknown) 인스턴스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="86fdf-107">[in] A pointer to an [IUnknown](/cpp/atl/iunknown) instance that serves as a function callback for validation errors.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="86fdf-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="86fdf-108">Requirements</span></span>  

 <span data-ttu-id="86fdf-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="86fdf-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="86fdf-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="86fdf-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="86fdf-111">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="86fdf-111">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="86fdf-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="86fdf-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86fdf-113">참조</span><span class="sxs-lookup"><span data-stu-id="86fdf-113">See also</span></span>

- [<span data-ttu-id="86fdf-114">IMetaDataValidate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="86fdf-114">IMetaDataValidate Interface</span></span>](imetadatavalidate-interface.md)
