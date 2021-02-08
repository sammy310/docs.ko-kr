---
description: '자세히 알아보기: IMetaDataValidate 인터페이스'
title: IMetaDataValidate 인터페이스
ms.date: 03/30/2017
api_name:
- IMetaDataValidate
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataValidate
helpviewer_keywords:
- IMetaDataValidate interface [.NET Framework metadata]
ms.assetid: db98608a-e85c-4f50-9d7b-5f57a426ddb6
topic_type:
- apiref
ms.openlocfilehash: fbdbdf6880d7cb5ee6d4c21df587eb63b26b456e
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99799220"
---
# <a name="imetadatavalidate-interface"></a><span data-ttu-id="8a95d-103">IMetaDataValidate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a95d-103">IMetaDataValidate Interface</span></span>

<span data-ttu-id="8a95d-104">메타데이터 서명의 유효성을 검사할 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8a95d-104">Provides methods to validate metadata signatures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a95d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8a95d-105">Methods</span></span>  
  
|<span data-ttu-id="8a95d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8a95d-106">Method</span></span>|<span data-ttu-id="8a95d-107">설명</span><span class="sxs-lookup"><span data-stu-id="8a95d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a95d-108">ValidateMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="8a95d-108">ValidateMetaData Method</span></span>](imetadatavalidate-validatemetadata-method.md)|<span data-ttu-id="8a95d-109">현재 메타데이터 범위에서 개체에 대한 메타데이터 서명의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="8a95d-109">Validates the metadata signatures of the objects in the current metadata scope.</span></span>|  
|[<span data-ttu-id="8a95d-110">ValidatorInit 메서드</span><span class="sxs-lookup"><span data-stu-id="8a95d-110">ValidatorInit Method</span></span>](imetadatavalidate-validatorinit-method.md)|<span data-ttu-id="8a95d-111">현재 메타데이터 범위에서 모듈 형식을 지정하는 플래그를 설정하고 유효성 검사 오류에 대한 지정된 콜백 메서드를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="8a95d-111">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="8a95d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a95d-112">Requirements</span></span>  

 <span data-ttu-id="8a95d-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8a95d-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a95d-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="8a95d-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="8a95d-115">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8a95d-115">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="8a95d-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a95d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a95d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a95d-117">See also</span></span>

- [<span data-ttu-id="8a95d-118">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a95d-118">Metadata Interfaces</span></span>](metadata-interfaces.md)
