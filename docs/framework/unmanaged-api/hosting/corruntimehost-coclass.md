---
description: '자세한 정보: CorRuntimeHost Coclass'
title: CorRuntimeHost Coclass
ms.date: 03/30/2017
api_name:
- CorRuntimeHost Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorRuntimeHost
helpviewer_keywords:
- CoRuntimeHost coclass [.NET Framework hosting]
ms.assetid: 5833740b-7d67-44b4-865c-b5bf45e291e3
topic_type:
- apiref
ms.openlocfilehash: cd2d01075e5c8264337e1e989b3d9fdc6bf68962
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760643"
---
# <a name="corruntimehost-coclass"></a><span data-ttu-id="15869-103">CorRuntimeHost Coclass</span><span class="sxs-lookup"><span data-stu-id="15869-103">CorRuntimeHost Coclass</span></span>

<span data-ttu-id="15869-104">공용 언어 런타임에서 실행 되는 응용 프로그램을 관리 하기 위한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="15869-104">Provides interfaces for managing applications that are being executed by the common language runtime.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="15869-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="15869-105">Syntax</span></span>  
  
```cpp  
coclass CorRuntimeHost {  
    [default] interface ICorRuntimeHost;  
    interface IGCHost;  
    interface ICorConfiguration;  
    interface IValidator;  
    interface IDebuggerInfo;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="15869-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="15869-106">Interfaces</span></span>  
  
|<span data-ttu-id="15869-107">인터페이스</span><span class="sxs-lookup"><span data-stu-id="15869-107">Interface</span></span>|<span data-ttu-id="15869-108">설명</span><span class="sxs-lookup"><span data-stu-id="15869-108">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="15869-109">ICorConfiguration 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15869-109">ICorConfiguration Interface</span></span>](icorconfiguration-interface.md)|<span data-ttu-id="15869-110">CLR (공용 언어 런타임)을 구성 하는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="15869-110">Provides methods for configuring the common language runtime (CLR).</span></span>|  
|[<span data-ttu-id="15869-111">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15869-111">ICorRuntimeHost Interface</span></span>](icorruntimehost-interface.md)|<span data-ttu-id="15869-112">호스트에서 공용 언어 런타임을 명시적으로 시작 및 중지 하 고, 응용 프로그램 도메인을 만들고 구성 하 고, 기본 도메인에 액세스 하 고, 프로세스에서 실행 되는 모든 도메인을 열거 하는 데 사용할 수 있는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="15869-112">Provides methods that enable the host to start and stop the common language runtime explicitly, to create and configure application domains, to access the default domain, and to enumerate all domains running in the process.</span></span>|  
|[<span data-ttu-id="15869-113">IDebuggerInfo 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15869-113">IDebuggerInfo Interface</span></span>](idebuggerinfo-interface.md)|<span data-ttu-id="15869-114">디버깅 서비스의 상태에 대 한 정보를 가져오는 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="15869-114">Provides methods for obtaining information about the state of the debugging services.</span></span>|  
|[<span data-ttu-id="15869-115">IGCHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="15869-115">IGCHost Interface</span></span>](igchost-interface.md)|<span data-ttu-id="15869-116">가비지 컬렉션 시스템에 대 한 정보를 가져오고 가비지 수집의 일부 측면을 제어 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="15869-116">Provides methods for obtaining information about the garbage collection system and for controlling some aspects of garbage collection.</span></span>|  
|<span data-ttu-id="15869-117">IValidator</span><span class="sxs-lookup"><span data-stu-id="15869-117">"IValidator"</span></span>|<span data-ttu-id="15869-118">이식 가능한 실행 가능한 이미지의 유효성을 검사 하 고 유효성 검사 오류에 대 한 자세한 보고 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="15869-118">Provides methods for validation of portable executable images and detailed reporting of validation errors.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="15869-119">요구 사항</span><span class="sxs-lookup"><span data-stu-id="15869-119">Requirements</span></span>  

 <span data-ttu-id="15869-120">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="15869-120">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="15869-121">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="15869-121">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="15869-122">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="15869-122">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="15869-123">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="15869-123">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="15869-124">참고 항목</span><span class="sxs-lookup"><span data-stu-id="15869-124">See also</span></span>

- [<span data-ttu-id="15869-125">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="15869-125">Hosting Coclasses</span></span>](hosting-coclasses.md)
