---
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
author: mairaw
ms.author: mairaw
ms.openlocfilehash: 804c8c9434983b12b0647395c49197bf5026239b
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59180988"
---
# <a name="imetadatavalidate-interface"></a><span data-ttu-id="23314-102">IMetaDataValidate 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23314-102">IMetaDataValidate Interface</span></span>
<span data-ttu-id="23314-103">메타데이터 서명의 유효성을 검사할 메서드를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="23314-103">Provides methods to validate metadata signatures.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="23314-104">메서드</span><span class="sxs-lookup"><span data-stu-id="23314-104">Methods</span></span>  
  
|<span data-ttu-id="23314-105">메서드</span><span class="sxs-lookup"><span data-stu-id="23314-105">Method</span></span>|<span data-ttu-id="23314-106">설명</span><span class="sxs-lookup"><span data-stu-id="23314-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="23314-107">ValidateMetaData 메서드</span><span class="sxs-lookup"><span data-stu-id="23314-107">ValidateMetaData Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-validatemetadata-method.md)|<span data-ttu-id="23314-108">현재 메타데이터 범위에서 개체에 대한 메타데이터 서명의 유효성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="23314-108">Validates the metadata signatures of the objects in the current metadata scope.</span></span>|  
|[<span data-ttu-id="23314-109">ValidatorInit 메서드</span><span class="sxs-lookup"><span data-stu-id="23314-109">ValidatorInit Method</span></span>](../../../../docs/framework/unmanaged-api/metadata/imetadatavalidate-validatorinit-method.md)|<span data-ttu-id="23314-110">현재 메타데이터 범위에서 모듈 형식을 지정하는 플래그를 설정하고 유효성 검사 오류에 대한 지정된 콜백 메서드를 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="23314-110">Sets a flag that specifies the type of the module in the current metadata scope, and registers the specified callback method for validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="23314-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="23314-111">Requirements</span></span>  
 <span data-ttu-id="23314-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="23314-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="23314-113">**헤더:** Cor.h</span><span class="sxs-lookup"><span data-stu-id="23314-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="23314-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용</span><span class="sxs-lookup"><span data-stu-id="23314-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="23314-115">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="23314-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23314-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="23314-116">See also</span></span>

- [<span data-ttu-id="23314-117">메타데이터 인터페이스</span><span class="sxs-lookup"><span data-stu-id="23314-117">Metadata Interfaces</span></span>](../../../../docs/framework/unmanaged-api/metadata/metadata-interfaces.md)
