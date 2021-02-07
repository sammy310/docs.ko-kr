---
description: '자세히 알아보기: IValidator 인터페이스'
title: IValidator 인터페이스
ms.date: 03/30/2017
api_name:
- IValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IValidator
helpviewer_keywords:
- IValidator interface [.NET Framework hosting]
ms.assetid: b297e3b0-20f9-478f-b707-5e2eecb2b5b2
topic_type:
- apiref
ms.openlocfilehash: bc18b68d0e9a0e978789ab92afaed28751925870
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99680098"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="fac4f-103">IValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fac4f-103">IValidator Interface</span></span>

<span data-ttu-id="fac4f-104">PE (이식 가능한 실행) 이미지를 확인 하 고 유효성 검사 오류를 보고 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac4f-104">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="fac4f-105">메서드</span><span class="sxs-lookup"><span data-stu-id="fac4f-105">Methods</span></span>  
  
|<span data-ttu-id="fac4f-106">메서드</span><span class="sxs-lookup"><span data-stu-id="fac4f-106">Method</span></span>|<span data-ttu-id="fac4f-107">Description</span><span class="sxs-lookup"><span data-stu-id="fac4f-107">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="fac4f-108">유효성 검사</span><span class="sxs-lookup"><span data-stu-id="fac4f-108">Validate</span></span>|<span data-ttu-id="fac4f-109">지정 된 PE 또는 MSIL (Microsoft 중간 언어) 파일의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="fac4f-109">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="fac4f-110">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="fac4f-110">FormatEventInfo</span></span>|<span data-ttu-id="fac4f-111">지정 된 유효성 검사 오류에 해당 하는 오류 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="fac4f-111">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="fac4f-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fac4f-112">Requirements</span></span>  

 <span data-ttu-id="fac4f-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fac4f-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fac4f-114">**헤더:** IValidator, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="fac4f-114">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="fac4f-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fac4f-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fac4f-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fac4f-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fac4f-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fac4f-117">See also</span></span>

- [<span data-ttu-id="fac4f-118">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fac4f-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="fac4f-119">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="fac4f-119">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
