---
title: IMetaDataEmit::SetModuleProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataEmit.SetModuleProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataEmit::SetModuleProps
helpviewer_keywords:
- SetModuleProps method [.NET Framework metadata]
- IMetaDataEmit::SetModuleProps method [.NET Framework metadata]
ms.assetid: b74d7629-5f46-458f-8d67-2456a1e7030c
topic_type:
- apiref
ms.openlocfilehash: aee258c49e6726ebef990257456fd273b01b9ef0
ms.sourcegitcommit: 03fec33630b46e78d5e81e91b40518f32c4bd7b5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "84007847"
---
# <a name="imetadataemitsetmoduleprops-method"></a><span data-ttu-id="fd29e-102">IMetaDataEmit::SetModuleProps 메서드</span><span class="sxs-lookup"><span data-stu-id="fd29e-102">IMetaDataEmit::SetModuleProps Method</span></span>
<span data-ttu-id="fd29e-103">[IMetaDataEmit::D efinemoduleref](imetadataemit-definemoduleref-method.md)에 대 한 이전 호출로 정의 된 모듈에 대 한 참조를 업데이트 합니다.</span><span class="sxs-lookup"><span data-stu-id="fd29e-103">Updates references to a module defined by a prior call to [IMetaDataEmit::DefineModuleRef](imetadataemit-definemoduleref-method.md).</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="fd29e-104">구문</span><span class="sxs-lookup"><span data-stu-id="fd29e-104">Syntax</span></span>  
  
```cpp  
HRESULT SetModuleProps (
    [in]  LPCWSTR     szName  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="fd29e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="fd29e-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="fd29e-106">진행 유니코드의 모듈 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fd29e-106">[in] The module name in Unicode.</span></span> <span data-ttu-id="fd29e-107">전체 경로 이름이 아니라 파일 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="fd29e-107">This is the file name only and not the full path name.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="fd29e-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="fd29e-108">Requirements</span></span>  
 <span data-ttu-id="fd29e-109">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="fd29e-109">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="fd29e-110">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="fd29e-110">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="fd29e-111">**라이브러리:** Mscoree.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="fd29e-111">**Library:** Used as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="fd29e-112">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="fd29e-112">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fd29e-113">참고 항목</span><span class="sxs-lookup"><span data-stu-id="fd29e-113">See also</span></span>

- [<span data-ttu-id="fd29e-114">IMetaDataEmit 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd29e-114">IMetaDataEmit Interface</span></span>](imetadataemit-interface.md)
- [<span data-ttu-id="fd29e-115">IMetaDataEmit2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="fd29e-115">IMetaDataEmit2 Interface</span></span>](imetadataemit2-interface.md)
