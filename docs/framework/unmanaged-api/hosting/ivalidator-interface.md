---
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
ms.openlocfilehash: d8e5ab607f9310341ded482b35f02f3845926328
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84008562"
---
# <a name="ivalidator-interface"></a><span data-ttu-id="f7d0d-102">IValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7d0d-102">IValidator Interface</span></span>
<span data-ttu-id="f7d0d-103">PE (이식 가능한 실행) 이미지를 확인 하 고 유효성 검사 오류를 보고 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d0d-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="f7d0d-104">메서드</span><span class="sxs-lookup"><span data-stu-id="f7d0d-104">Methods</span></span>  
  
|<span data-ttu-id="f7d0d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="f7d0d-105">Method</span></span>|<span data-ttu-id="f7d0d-106">Description</span><span class="sxs-lookup"><span data-stu-id="f7d0d-106">Description</span></span>|  
|------------|-----------------|  
|<span data-ttu-id="f7d0d-107">유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f7d0d-107">Validate</span></span>|<span data-ttu-id="f7d0d-108">지정 된 PE 또는 MSIL (Microsoft 중간 언어) 파일의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="f7d0d-108">Validates the specified PE or Microsoft intermediate language (MSIL) file.</span></span>|  
|<span data-ttu-id="f7d0d-109">FormatEventInfo</span><span class="sxs-lookup"><span data-stu-id="f7d0d-109">FormatEventInfo</span></span>|<span data-ttu-id="f7d0d-110">지정 된 유효성 검사 오류에 해당 하는 오류 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="f7d0d-110">Gets the error message corresponding to the specified validation error.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="f7d0d-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f7d0d-111">Requirements</span></span>  
 <span data-ttu-id="f7d0d-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="f7d0d-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f7d0d-113">**헤더:** IValidator, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="f7d0d-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="f7d0d-114">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="f7d0d-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="f7d0d-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f7d0d-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f7d0d-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f7d0d-116">See also</span></span>

- [<span data-ttu-id="f7d0d-117">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f7d0d-117">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="f7d0d-118">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="f7d0d-118">CorRuntimeHost Coclass</span></span>](corruntimehost-coclass.md)
