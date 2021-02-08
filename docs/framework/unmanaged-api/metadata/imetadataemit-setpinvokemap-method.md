---
description: '자세히 알아보기: IMetaDataEmit:: SetPinvokeMap 메서드'
title: IMetaDataEmit::SetPinvokeMap 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetPinvokeMap
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetPinvokeMap
helpviewer_keywords:
- IMetaDataEmit::SetPinvokeMap method [.NET Framework metadata]
- SetPinvokeMap method [.NET Framework metadata]
ms.assetid: c6bfd574-1da3-4ba7-82f2-46ca5efcbaba
topic_type:
- apiref
ms.openlocfilehash: e50f06385b599a99454da0a9b971b00806d3140a
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99771849"
---
# <a name="imetadataemitsetpinvokemap-method"></a><span data-ttu-id="64ee3-103">IMetaDataEmit::SetPinvokeMap 메서드</span><span class="sxs-lookup"><span data-stu-id="64ee3-103">IMetaDataEmit::SetPinvokeMap Method</span></span>

<span data-ttu-id="64ee3-104">[IMetaDataEmit::D efinepinvokemap](imetadataemit-definepinvokemap-method.md)에 대 한 이전 호출에서 정의한 대로 메서드 PInvoke 시그니처의 기능을 설정 하거나 변경 합니다.</span><span class="sxs-lookup"><span data-stu-id="64ee3-104">Sets or changes features of a method's PInvoke signature, as defined by a prior call to [IMetaDataEmit::DefinePinvokeMap](imetadataemit-definepinvokemap-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="64ee3-105">구문</span><span class="sxs-lookup"><span data-stu-id="64ee3-105">Syntax</span></span>  
  
```cpp  
HRESULT SetPinvokeMap (
    [in]  mdToken      tk,
    [in]  DWORD        dwMappingFlags,  
    [in]  LPCWSTR      szImportName,
    [in]  mdModuleRef  mrImportDLL
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="64ee3-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="64ee3-106">Parameters</span></span>  

 `tk`  
 <span data-ttu-id="64ee3-107">진행 `mdToken` 매핑 정보가 적용 되는입니다.</span><span class="sxs-lookup"><span data-stu-id="64ee3-107">[in] The `mdToken` to which mapping information applies.</span></span>  
  
 `dwMappingFlags`  
 <span data-ttu-id="64ee3-108">진행 PInvoke에서 매핑을 수행 하는 데 사용 되는 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="64ee3-108">[in] Flags used by PInvoke to do the mapping.</span></span> <span data-ttu-id="64ee3-109">값의 비트 마스크입니다 `CorPinvokeMap` .</span><span class="sxs-lookup"><span data-stu-id="64ee3-109">This is a bitmask of `CorPinvokeMap` values.</span></span>  
  
 `szImportName`  
 <span data-ttu-id="64ee3-110">진행 네이티브 DLL의 대상 내보내기 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="64ee3-110">[in] The name of the target export in the native DLL.</span></span>  
  
 `mrImportDLL`  
 <span data-ttu-id="64ee3-111">진행 `mdModuleRef` 관리 되지 않는 대상 DLL에 대 한 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="64ee3-111">[in] The `mdModuleRef` token for the target unmanaged DLL.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="64ee3-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="64ee3-112">Requirements</span></span>  

 <span data-ttu-id="64ee3-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="64ee3-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="64ee3-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="64ee3-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="64ee3-115">**라이브러리:** MSCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="64ee3-115">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="64ee3-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="64ee3-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="64ee3-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="64ee3-117">See also</span></span>

- [<span data-ttu-id="64ee3-118">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64ee3-118">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="64ee3-119">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="64ee3-119">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
