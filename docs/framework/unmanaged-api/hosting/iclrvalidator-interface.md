---
description: '자세히 알아보기: ICLRValidator 인터페이스'
title: ICLRValidator 인터페이스
ms.date: 03/30/2017
api_name:
- ICLRValidator
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- ICLRValidator
helpviewer_keywords:
- ICLRValidator interface [.NET Framework hosting]
ms.assetid: 2edd0a10-77fb-4173-91eb-f2970cc364d0
topic_type:
- apiref
ms.openlocfilehash: 72ff94915d35967b6a8a87b022789ca697f61711
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99636756"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="87fba-103">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87fba-103">ICLRValidator Interface</span></span>

<span data-ttu-id="87fba-104">PE (이식 가능한 실행) 이미지를 확인 하 고 유효성 검사 오류를 보고 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="87fba-104">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="87fba-105">메서드</span><span class="sxs-lookup"><span data-stu-id="87fba-105">Methods</span></span>  
  
|<span data-ttu-id="87fba-106">메서드</span><span class="sxs-lookup"><span data-stu-id="87fba-106">Method</span></span>|<span data-ttu-id="87fba-107">설명</span><span class="sxs-lookup"><span data-stu-id="87fba-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="87fba-108">FormatEventInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="87fba-108">FormatEventInfo Method</span></span>](iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="87fba-109">지정 된 유효성 검사 오류에 대 한 자세한 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="87fba-109">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="87fba-110">Validate 메서드</span><span class="sxs-lookup"><span data-stu-id="87fba-110">Validate Method</span></span>](iclrvalidator-validate-method.md)|<span data-ttu-id="87fba-111">지정 된 파일에서 이식 가능한 실행 파일이 나 MSIL (Microsoft 중간 언어)의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="87fba-111">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="87fba-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="87fba-112">Requirements</span></span>  

 <span data-ttu-id="87fba-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="87fba-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="87fba-114">**헤더:** IValidator, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="87fba-114">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="87fba-115">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="87fba-115">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="87fba-116">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="87fba-116">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="87fba-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="87fba-117">See also</span></span>

- [<span data-ttu-id="87fba-118">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87fba-118">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="87fba-119">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="87fba-119">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="87fba-120">CLRRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="87fba-120">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
