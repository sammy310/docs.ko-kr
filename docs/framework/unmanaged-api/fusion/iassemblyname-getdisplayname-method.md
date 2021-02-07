---
description: '자세히 알아보기: IAssemblyName:: GetDisplayName 메서드'
title: IAssemblyName::GetDisplayName 메서드
ms.date: 03/30/2017
api_name:
- IAssemblyName.GetDisplayName
api_location:
- fusion.dll
api_type:
- COM
f1_keywords:
- IAssemblyName::GetDisplayName
helpviewer_keywords:
- GetDisplayName method, IAssemblyName interface [.NET Framework fusion]
- IAssemblyName::GetDisplayName method [.NET Framework fusion]
ms.assetid: 9a26547a-9a34-4284-a463-78a7d4b496cf
topic_type:
- apiref
ms.openlocfilehash: 9b52a901385fa9b3ba7cb6bcd1678d0718f8f695
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99760760"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="9dc2b-103">IAssemblyName::GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="9dc2b-103">IAssemblyName::GetDisplayName Method</span></span>

<span data-ttu-id="9dc2b-104">이 [IAssemblyName](iassemblyname-interface.md) 개체가 참조 하는 어셈블리의 사람이 읽을 수 있는 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="9dc2b-104">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="9dc2b-105">구문</span><span class="sxs-lookup"><span data-stu-id="9dc2b-105">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="9dc2b-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="9dc2b-106">Parameters</span></span>  

 `szDisplayName`  
 <span data-ttu-id="9dc2b-107">제한이 참조 된 어셈블리의 이름을 포함 하는 문자열 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc2b-107">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="9dc2b-108">[in, out] `szDisplayName` Null 종결자 문자를 포함 하는 와이드 문자 단위의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="9dc2b-108">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="9dc2b-109">진행 의 기능에 영향을 주는 [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) 값의 비트 조합입니다 `szDisplayName` .</span><span class="sxs-lookup"><span data-stu-id="9dc2b-109">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="9dc2b-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="9dc2b-110">Requirements</span></span>  

 <span data-ttu-id="9dc2b-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="9dc2b-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="9dc2b-112">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="9dc2b-112">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="9dc2b-113">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="9dc2b-113">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9dc2b-114">참고 항목</span><span class="sxs-lookup"><span data-stu-id="9dc2b-114">See also</span></span>

- [<span data-ttu-id="9dc2b-115">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="9dc2b-115">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="9dc2b-116">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="9dc2b-116">Fusion Enumerations</span></span>](fusion-enumerations.md)
