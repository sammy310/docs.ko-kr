---
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
ms.openlocfilehash: d9ccd5c6c91b1ab2166ff40a0fb2048e15927d3a
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95723950"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="56dea-102">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56dea-102">ICLRValidator Interface</span></span>

<span data-ttu-id="56dea-103">PE (이식 가능한 실행) 이미지를 확인 하 고 유효성 검사 오류를 보고 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="56dea-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="56dea-104">메서드</span><span class="sxs-lookup"><span data-stu-id="56dea-104">Methods</span></span>  
  
|<span data-ttu-id="56dea-105">메서드</span><span class="sxs-lookup"><span data-stu-id="56dea-105">Method</span></span>|<span data-ttu-id="56dea-106">설명</span><span class="sxs-lookup"><span data-stu-id="56dea-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="56dea-107">FormatEventInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="56dea-107">FormatEventInfo Method</span></span>](iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="56dea-108">지정 된 유효성 검사 오류에 대 한 자세한 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="56dea-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="56dea-109">Validate 메서드</span><span class="sxs-lookup"><span data-stu-id="56dea-109">Validate Method</span></span>](iclrvalidator-validate-method.md)|<span data-ttu-id="56dea-110">지정 된 파일에서 이식 가능한 실행 파일이 나 MSIL (Microsoft 중간 언어)의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="56dea-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="56dea-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="56dea-111">Requirements</span></span>  

 <span data-ttu-id="56dea-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="56dea-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="56dea-113">**헤더:** IValidator, IValidator. h</span><span class="sxs-lookup"><span data-stu-id="56dea-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="56dea-114">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="56dea-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="56dea-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="56dea-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="56dea-116">참조</span><span class="sxs-lookup"><span data-stu-id="56dea-116">See also</span></span>

- [<span data-ttu-id="56dea-117">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56dea-117">ICLRErrorReportingManager Interface</span></span>](iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="56dea-118">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="56dea-118">Hosting Interfaces</span></span>](hosting-interfaces.md)
- [<span data-ttu-id="56dea-119">CLRRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="56dea-119">CLRRuntimeHost Coclass</span></span>](clrruntimehost-coclass.md)
