---
title: IMetaDataImport::GetScopeProps 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataImport.GetScopeProps
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataImport::GetScopeProps
helpviewer_keywords:
- IMetaDataImport::GetScopeProps method [.NET Framework metadata]
- GetScopeProps method [.NET Framework metadata]
ms.assetid: c8ba42d2-d9fa-43cb-bbc0-f33e1e592cb6
topic_type:
- apiref
ms.openlocfilehash: 0916b6382bb9352616d85e21f423301dc6aa9fa9
ms.sourcegitcommit: da21fc5a8cce1e028575acf31974681a1bc5aeed
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2020
ms.locfileid: "84490850"
---
# <a name="imetadataimportgetscopeprops-method"></a><span data-ttu-id="6c7c5-102">IMetaDataImport::GetScopeProps 메서드</span><span class="sxs-lookup"><span data-stu-id="6c7c5-102">IMetaDataImport::GetScopeProps Method</span></span>
<span data-ttu-id="6c7c5-103">현재 메타데이터 범위에서 어셈블리 또는 모듈의 이름과 선택적으로 버전 식별자를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="6c7c5-103">Gets the name and optionally the version identifier of the assembly or module in the current metadata scope.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="6c7c5-104">구문</span><span class="sxs-lookup"><span data-stu-id="6c7c5-104">Syntax</span></span>  
  
```cpp  
HRESULT GetScopeProps (  
   [out] LPWSTR           szName,  
   [in]  ULONG            cchName,  
   [out] ULONG            *pchName,  
   [out, optional] GUID   *pmvid  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="6c7c5-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="6c7c5-105">Parameters</span></span>  
 `szName`  
 <span data-ttu-id="6c7c5-106">제한이 어셈블리 또는 모듈 이름에 대 한 버퍼입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7c5-106">[out] A buffer for the assembly or module name.</span></span>  
  
 `cchName`  
 <span data-ttu-id="6c7c5-107">진행 의 와이드 문자 크기입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="6c7c5-107">[in] The size in wide characters of `szName`.</span></span>  
  
 `pchName`  
 <span data-ttu-id="6c7c5-108">제한이 에서 반환 되는 와이드 문자 수입니다 `szName` .</span><span class="sxs-lookup"><span data-stu-id="6c7c5-108">[out] The number of wide characters returned in `szName`.</span></span>  
  
 `pmvid`  
 <span data-ttu-id="6c7c5-109">[out, 선택 사항] 어셈블리 또는 모듈의 버전을 고유 하 게 식별 하는 GUID에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="6c7c5-109">[out, optional] A pointer to a GUID that uniquely identifies the version of the assembly or module.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="6c7c5-110">설명</span><span class="sxs-lookup"><span data-stu-id="6c7c5-110">Remarks</span></span>  
 <span data-ttu-id="6c7c5-111">[IMetaDataEmit:: SetModuleProps](imetadataemit-setmoduleprops-method.md) 메서드는 이러한 속성을 설정 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7c5-111">The [IMetaDataEmit::SetModuleProps](imetadataemit-setmoduleprops-method.md) method is used to set these properties.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="6c7c5-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="6c7c5-112">Requirements</span></span>  
 <span data-ttu-id="6c7c5-113">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="6c7c5-113">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="6c7c5-114">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="6c7c5-114">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="6c7c5-115">**라이브러리:** Mscoree.dll에 리소스로 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="6c7c5-115">**Library:** Included as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="6c7c5-116">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="6c7c5-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6c7c5-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="6c7c5-117">See also</span></span>

- [<span data-ttu-id="6c7c5-118">IMetaDataImport 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c7c5-118">IMetaDataImport Interface</span></span>](imetadataimport-interface.md)
- [<span data-ttu-id="6c7c5-119">IMetaDataImport2 인터페이스</span><span class="sxs-lookup"><span data-stu-id="6c7c5-119">IMetaDataImport2 Interface</span></span>](imetadataimport2-interface.md)
