---
description: '자세히 알아보기: TypeNameFactory Coclass'
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
ms.openlocfilehash: 937f34f5b8dd78df87efae3ab30d8e6f34f66ac3
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99679253"
---
# <a name="typenamefactory-coclass"></a><span data-ttu-id="1c0d5-103">TypeNameFactory Coclass</span><span class="sxs-lookup"><span data-stu-id="1c0d5-103">TypeNameFactory Coclass</span></span>

<span data-ttu-id="1c0d5-104">형식 이름의 분해를 관리 하기 위한 인터페이스를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="1c0d5-104">Provides an interface for managing the deconstruction of a type name.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="1c0d5-105">Syntax</span><span class="sxs-lookup"><span data-stu-id="1c0d5-105">Syntax</span></span>  
  
```cpp  
coclass TypeNameFactory {  
    [default] interface ITypeNameFactory;  
};  
```  
  
## <a name="interfaces"></a><span data-ttu-id="1c0d5-106">인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c0d5-106">Interfaces</span></span>  
  
|<span data-ttu-id="1c0d5-107">인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c0d5-107">Interface</span></span>|<span data-ttu-id="1c0d5-108">설명</span><span class="sxs-lookup"><span data-stu-id="1c0d5-108">Description</span></span>|  
|---------------|-----------------|  
|[<span data-ttu-id="1c0d5-109">ITypeNameFactory 인터페이스</span><span class="sxs-lookup"><span data-stu-id="1c0d5-109">ITypeNameFactory Interface</span></span>](itypenamefactory-interface.md)|<span data-ttu-id="1c0d5-110">이 인터페이스는 .NET Framework 인프라를 지원하며 사용자 코드에서 직접 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="1c0d5-110">This interface supports the .NET Framework infrastructure and is not intended to be used directly from your code.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="1c0d5-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="1c0d5-111">Requirements</span></span>  

 <span data-ttu-id="1c0d5-112">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1c0d5-112">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="1c0d5-113">**헤더:** Mscoree.dll</span><span class="sxs-lookup"><span data-stu-id="1c0d5-113">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="1c0d5-114">**라이브러리:** MSCorEE.dll의 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1c0d5-114">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="1c0d5-115">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="1c0d5-115">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c0d5-116">참고 항목</span><span class="sxs-lookup"><span data-stu-id="1c0d5-116">See also</span></span>

- [<span data-ttu-id="1c0d5-117">호스팅 Coclass</span><span class="sxs-lookup"><span data-stu-id="1c0d5-117">Hosting Coclasses</span></span>](hosting-coclasses.md)
