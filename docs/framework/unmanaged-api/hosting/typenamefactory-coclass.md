---
title: TypeNameFactory Coclass
ms.date: 03/30/2017
api_name:
- TypeNameFactory Coclass
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- TypeNameFactory
helpviewer_keywords:
- TypeNameFactory coclass [.NET Framework hosting]
ms.assetid: c853bb58-c9c5-476b-8e80-608aa53ea18d
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 14266f02dd402e81928b72d155f224e10e910592
ms.sourcegitcommit: 7f616512044ab7795e32806578e8dc0c6a0e038f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/10/2019
ms.locfileid: "67781241"
---
# <a name="typenamefactory-coclass"></a><span data-ttu-id="38a8c-102">TypeNameFactory Coclass</span><span class="sxs-lookup"><span data-stu-id="38a8c-102">TypeNameFactory Coclass</span></span>
<span data-ttu-id="38a8c-103">형식 이름의 분해를 관리 하는 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="38a8c-103">Provides an interface for managing the deconstruction of a type name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="38a8c-104">구문</span><span class="sxs-lookup"><span data-stu-id="38a8c-104">Syntax</span></span>  
  
```cpp  
coclass TypeNameFactory {  
    [default] interface ITypeNameFactory;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="38a8c-105">인터페이스</span><span class="sxs-lookup"><span data-stu-id="38a8c-105">Interfaces</span></span>  
  
|<span data-ttu-id="38a8c-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="38a8c-106">Interface</span></span>|<span data-ttu-id="38a8c-107">Description</span><span class="sxs-lookup"><span data-stu-id="38a8c-107">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="38a8c-108">ITypeNameFactory 인터페이스</span><span class="sxs-lookup"><span data-stu-id="38a8c-108">ITypeNameFactory Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/itypenamefactory-interface.md)|<span data-ttu-id="38a8c-109">이 인터페이스는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="38a8c-109">This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="38a8c-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="38a8c-110">Requirements</span></span>  
 <span data-ttu-id="38a8c-111">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="38a8c-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="38a8c-112">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="38a8c-112">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="38a8c-113">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="38a8c-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="38a8c-114">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="38a8c-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="38a8c-115">참고자료</span><span class="sxs-lookup"><span data-stu-id="38a8c-115">See also</span></span>

- [<span data-ttu-id="38a8c-116">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="38a8c-116">Hosting Coclasses</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-coclasses.md)
