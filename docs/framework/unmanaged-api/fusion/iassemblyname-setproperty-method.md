---
description: '자세히 알아보기: IAssemblyName:: SetProperty 메서드'
title: IAssemblyName::SetProperty 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.SetProperty
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::SetProperty
helpviewer_keywords:
- IAssemblyName::SetProperty method [.NET Framework fusion]
- SetProperty method [.NET Framework fusion]
ms.assetid: 496c3add-f60b-4073-943f-d1bcf33330cb
topic_type:
- apiref
ms.openlocfilehash: cab132c2cd8a0744a2a946a1d8b21f49012c6eac
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760690"
---
# <a name="iassemblynamesetproperty-method"></a><span data-ttu-id="06e29-103">IAssemblyName::SetProperty 메서드</span><span class="sxs-lookup"><span data-stu-id="06e29-103">IAssemblyName::SetProperty Method</span></span>

<span data-ttu-id="06e29-104">지정 된 속성 식별자가 참조 하는 속성의 값을 설정 합니다.</span><span class="sxs-lookup"><span data-stu-id="06e29-104">Sets the value of the property referenced by the specified property identifier.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="06e29-105">구문</span><span class="sxs-lookup"><span data-stu-id="06e29-105">Syntax</span></span>  
  
```cpp  
HRESULT SetProperty (  
    [in] DWORD  PropertyId,  
    [in] LPVOID pvProperty,  
    [in] DWORD  cbProperty  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="06e29-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="06e29-106">Parameters</span></span>  

 `PropertyId`  
 <span data-ttu-id="06e29-107">진행 값을 설정할 속성의 고유 식별자입니다.</span><span class="sxs-lookup"><span data-stu-id="06e29-107">[in] The unique identifier of the property whose value will be set.</span></span>  
  
 `pvProperty`  
 <span data-ttu-id="06e29-108">진행 에서 참조 하는 속성을 설정 하는 데 사용할 값입니다 `PropertyId` .</span><span class="sxs-lookup"><span data-stu-id="06e29-108">[in] The value to which to set the property referenced by `PropertyId`.</span></span>  
  
 `cbProperty`  
 <span data-ttu-id="06e29-109">진행 의 크기 (바이트)입니다 `pvProperty` .</span><span class="sxs-lookup"><span data-stu-id="06e29-109">[in] The size, in bytes, of `pvProperty`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="06e29-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="06e29-110">Requirements</span></span>  

 <span data-ttu-id="06e29-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="06e29-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="06e29-112">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="06e29-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="06e29-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="06e29-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="06e29-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="06e29-114">See also</span></span>

- [<span data-ttu-id="06e29-115">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="06e29-115">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
