---
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
ms.openlocfilehash: 5dbb5dc483bc5a08c59606654d55b5a62266e509
ms.sourcegitcommit: 559fcfbe4871636494870a8b716bf7325df34ac5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/30/2019
ms.locfileid: "73134374"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="2329a-102">IAssemblyName::GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="2329a-102">IAssemblyName::GetDisplayName Method</span></span>
<span data-ttu-id="2329a-103">이 [IAssemblyName](iassemblyname-interface.md) 개체가 참조 하는 어셈블리의 사람이 읽을 수 있는 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="2329a-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="2329a-104">구문</span><span class="sxs-lookup"><span data-stu-id="2329a-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="2329a-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="2329a-105">Parameters</span></span>  
 `szDisplayName`  
 <span data-ttu-id="2329a-106">제한이 참조 된 어셈블리의 이름을 포함 하는 문자열 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="2329a-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="2329a-107">[in, out] Null 종결자 문자를 포함 하 여 와이드 문자 `szDisplayName` 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="2329a-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="2329a-108">진행 `szDisplayName`의 기능에 영향을 주는 [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) 값의 비트 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="2329a-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="2329a-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2329a-109">Requirements</span></span>  
 <span data-ttu-id="2329a-110">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2329a-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2329a-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="2329a-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="2329a-112">**.NET Framework 버전:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2329a-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2329a-113">참조</span><span class="sxs-lookup"><span data-stu-id="2329a-113">See also</span></span>

- [<span data-ttu-id="2329a-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2329a-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="2329a-115">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="2329a-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
