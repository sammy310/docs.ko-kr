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
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 05287d3674e55a87cfe359fc08f74fa46000d79f
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59075849"
---
# <a name="iclrvalidator-interface"></a><span data-ttu-id="78553-102">ICLRValidator 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78553-102">ICLRValidator Interface</span></span>
<span data-ttu-id="78553-103">이식 가능한 실행 파일 (PE) 이미지 유효성 검사 및 유효성 검사 오류를 보고에 대 한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="78553-103">Provides methods for validating portable executable (PE) images and reporting validation errors.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="78553-104">메서드</span><span class="sxs-lookup"><span data-stu-id="78553-104">Methods</span></span>  
  
|<span data-ttu-id="78553-105">메서드</span><span class="sxs-lookup"><span data-stu-id="78553-105">Method</span></span>|<span data-ttu-id="78553-106">설명</span><span class="sxs-lookup"><span data-stu-id="78553-106">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="78553-107">FormatEventInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="78553-107">FormatEventInfo Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-formateventinfo-method.md)|<span data-ttu-id="78553-108">지정 된 유효성 검사 오류에 대 한 자세한 메시지를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="78553-108">Gets a detailed message about the specified validation error.</span></span>|  
|[<span data-ttu-id="78553-109">Validate 메서드</span><span class="sxs-lookup"><span data-stu-id="78553-109">Validate Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrvalidator-validate-method.md)|<span data-ttu-id="78553-110">이식 가능한 실행 파일 또는 MSIL (Microsoft intermediate language) 지정된 된 파일의 유효성을 검사 합니다.</span><span class="sxs-lookup"><span data-stu-id="78553-110">Validates the portable executable or Microsoft intermediate language (MSIL) in the specified file.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="78553-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="78553-111">Requirements</span></span>  
 <span data-ttu-id="78553-112">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="78553-112">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="78553-113">**헤더:** IValidator.idl, IValidator.h</span><span class="sxs-lookup"><span data-stu-id="78553-113">**Header:** IValidator.idl, IValidator.h</span></span>  
  
 <span data-ttu-id="78553-114">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="78553-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 **<span data-ttu-id="78553-115">.NET Framework 버전:</span><span class="sxs-lookup"><span data-stu-id="78553-115">.NET Framework Versions:</span></span>** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="78553-116">참고자료</span><span class="sxs-lookup"><span data-stu-id="78553-116">See also</span></span>

- [<span data-ttu-id="78553-117">ICLRErrorReportingManager 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78553-117">ICLRErrorReportingManager Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/iclrerrorreportingmanager-interface.md)
- [<span data-ttu-id="78553-118">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="78553-118">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)
- [<span data-ttu-id="78553-119">CLRRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="78553-119">CLRRuntimeHost Coclass</span></span>](../../../../docs/framework/unmanaged-api/hosting/clrruntimehost-coclass.md)
