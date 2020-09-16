---
title: IMetaDataDispenserEx::OpenScopeOnITypeInfo 메서드
ms.date: 03/30/2017
api_name:
- IMetaDataDispenserEx.OpenScopeOnITypeInfo
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- IMetaDataDispenserEx::OpenScopeOnITypeInfo
helpviewer_keywords:
- OpenScopeOnITypeInfo method [.NET Framework metadata]
- IMetaDataDispenserEx::OpenScopeOnITypeInfo method [.NET Framework metadata]
ms.assetid: 3480bbdb-c442-44a0-b7c6-333354503c52
topic_type:
- apiref
ms.openlocfilehash: 8e119093800ea0a0119ba25ba38cf2eaf9afe96b
ms.sourcegitcommit: 27a15a55019f6b5f2733961738babe94aec0def3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/15/2020
ms.locfileid: "90540864"
---
# <a name="imetadatadispenserexopenscopeonitypeinfo-method"></a><span data-ttu-id="582ac-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo 메서드</span><span class="sxs-lookup"><span data-stu-id="582ac-102">IMetaDataDispenserEx::OpenScopeOnITypeInfo Method</span></span>
<span data-ttu-id="582ac-103">이 메서드가 구현되지 않은 경우</span><span class="sxs-lookup"><span data-stu-id="582ac-103">This method is not implemented.</span></span> <span data-ttu-id="582ac-104">이 메서드를 호출 하면 E_NOTIMPL 반환 됩니다.</span><span class="sxs-lookup"><span data-stu-id="582ac-104">If called, it returns E_NOTIMPL.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="582ac-105">구문</span><span class="sxs-lookup"><span data-stu-id="582ac-105">Syntax</span></span>  
  
```cpp  
HRESULT OpenScopeOnITypeInfo (  
    [in]  ITypeInfo   *pITI,  
    [in]  DWORD       dwOpenFlags,  
    [in]  REFIID      riid,  
    [out] IUnknown    **ppIUnk  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="582ac-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="582ac-106">Parameters</span></span>  
 `pITI`  
 <span data-ttu-id="582ac-107">진행 범위를 열 수 있는 형식 정보를 제공 하는 [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) 인터페이스에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="582ac-107">[in] Pointer to an [ITypeInfo](/previous-versions/windows/desktop/api/oaidl/nn-oaidl-itypeinfo) interface that provides the type information on which to open the scope.</span></span>  
  
 `dwOpenFlags`  
 <span data-ttu-id="582ac-108">진행 열기 모드 플래그입니다.</span><span class="sxs-lookup"><span data-stu-id="582ac-108">[in] The open mode flags.</span></span>  
  
 `riid`  
 <span data-ttu-id="582ac-109">진행 원하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="582ac-109">[in] The desired interface.</span></span>  
  
 `ppIUnk`  
 <span data-ttu-id="582ac-110">제한이 반환 된 인터페이스에 대 한 포인터에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="582ac-110">[out] Pointer to a pointer to the returned interface.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="582ac-111">요구 사항</span><span class="sxs-lookup"><span data-stu-id="582ac-111">Requirements</span></span>  
 <span data-ttu-id="582ac-112">**플랫폼:** [시스템 요구 사항](../../get-started/system-requirements.md)을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="582ac-112">**Platform:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="582ac-113">**헤더:** Cor</span><span class="sxs-lookup"><span data-stu-id="582ac-113">**Header:** Cor.h</span></span>  
  
 <span data-ttu-id="582ac-114">**라이브러리:** MsCorEE.dll에서 리소스로 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="582ac-114">**Library:** Used as a resource in MsCorEE.dll</span></span>  
  
 <span data-ttu-id="582ac-115">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="582ac-115">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="582ac-116">참조</span><span class="sxs-lookup"><span data-stu-id="582ac-116">See also</span></span>

- [<span data-ttu-id="582ac-117">IMetaDataDispenserEx 인터페이스</span><span class="sxs-lookup"><span data-stu-id="582ac-117">IMetaDataDispenserEx Interface</span></span>](imetadatadispenserex-interface.md)
- [<span data-ttu-id="582ac-118">IMetaDataDispenser 인터페이스</span><span class="sxs-lookup"><span data-stu-id="582ac-118">IMetaDataDispenser Interface</span></span>](imetadatadispenser-interface.md)
