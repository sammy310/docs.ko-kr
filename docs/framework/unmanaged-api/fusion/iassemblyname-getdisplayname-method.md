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
ms.openlocfilehash: 13d71a9da2539c45076e5eb92e153e37c1df4b47
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95727915"
---
# <a name="iassemblynamegetdisplayname-method"></a><span data-ttu-id="ad557-102">IAssemblyName::GetDisplayName 메서드</span><span class="sxs-lookup"><span data-stu-id="ad557-102">IAssemblyName::GetDisplayName Method</span></span>

<span data-ttu-id="ad557-103">이 [IAssemblyName](iassemblyname-interface.md) 개체가 참조 하는 어셈블리의 사람이 읽을 수 있는 이름을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="ad557-103">Gets the human-readable name of the assembly referenced by this [IAssemblyName](iassemblyname-interface.md) object.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="ad557-104">구문</span><span class="sxs-lookup"><span data-stu-id="ad557-104">Syntax</span></span>  
  
```cpp  
HRESULT GetDisplayName (  
        [out]      LPOLESTR  szDisplayName,  
        [in, out]  LPDWORD   pccDisplayName,  
        [in]       DWORD     dwDisplayFlags  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="ad557-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="ad557-105">Parameters</span></span>  

 `szDisplayName`  
 <span data-ttu-id="ad557-106">제한이 참조 된 어셈블리의 이름을 포함 하는 문자열 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="ad557-106">[out] The string buffer that contains the name of the referenced assembly.</span></span>  
  
 `pccDisplayName`  
 <span data-ttu-id="ad557-107">[in, out] `szDisplayName` Null 종결자 문자를 포함 하는 와이드 문자 단위의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="ad557-107">[in, out] The size of `szDisplayName` in wide characters, including a null terminator character.</span></span>  
  
 `dwDisplayFlags`  
 <span data-ttu-id="ad557-108">진행 의 기능에 영향을 주는 [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) 값의 비트 조합입니다 `szDisplayName` .</span><span class="sxs-lookup"><span data-stu-id="ad557-108">[in] A bitwise combination of [ASM_DISPLAY_FLAGS](asm-display-flags-enumeration.md) values that influence the features of `szDisplayName`.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="ad557-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="ad557-109">Requirements</span></span>  

 <span data-ttu-id="ad557-110">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="ad557-110">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="ad557-111">**헤더:** Fusion. h</span><span class="sxs-lookup"><span data-stu-id="ad557-111">**Header:** Fusion.h</span></span>  
  
 <span data-ttu-id="ad557-112">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="ad557-112">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="ad557-113">참조</span><span class="sxs-lookup"><span data-stu-id="ad557-113">See also</span></span>

- [<span data-ttu-id="ad557-114">IAssemblyName 인터페이스</span><span class="sxs-lookup"><span data-stu-id="ad557-114">IAssemblyName Interface</span></span>](iassemblyname-interface.md)
- [<span data-ttu-id="ad557-115">Fusion 열거형</span><span class="sxs-lookup"><span data-stu-id="ad557-115">Fusion Enumerations</span></span>](fusion-enumerations.md)
