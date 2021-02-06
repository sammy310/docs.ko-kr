---
description: '자세히 알아보기: ICorDebugModule:: GetToken 메서드'
title: ICorDebugModule::GetToken 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugModule.GetToken
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugModule::GetToken
helpviewer_keywords:
- ICorDebugModule::GetToken method [.NET Framework debugging]
- GetToken method, ICorDebugModule interface [.NET Framework debugging]
ms.assetid: f759f87a-18ae-4c1a-8300-29b803432d0a
topic_type:
- apiref
ms.openlocfilehash: fd1bc4bc397e7f81c77f2fe784c68dbaaceb2695
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99660169"
---
# <a name="icordebugmodulegettoken-method"></a><span data-ttu-id="8f6a9-103">ICorDebugModule::GetToken 메서드</span><span class="sxs-lookup"><span data-stu-id="8f6a9-103">ICorDebugModule::GetToken Method</span></span>

<span data-ttu-id="8f6a9-104">이 모듈의 테이블 항목에 대 한 토큰을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8f6a9-104">Gets the token for the table entry for this module.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="8f6a9-105">구문</span><span class="sxs-lookup"><span data-stu-id="8f6a9-105">Syntax</span></span>  
  
```cpp  
HRESULT GetToken(  
    [out] mdModule *pToken  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="8f6a9-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="8f6a9-106">Parameters</span></span>  

 `pToken`  
 <span data-ttu-id="8f6a9-107">제한이 `mdModule` 모듈의 메타 데이터를 참조 하는 토큰에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="8f6a9-107">[out] A pointer to the `mdModule` token that references the module's metadata.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="8f6a9-108">설명</span><span class="sxs-lookup"><span data-stu-id="8f6a9-108">Remarks</span></span>  

 <span data-ttu-id="8f6a9-109">토큰은 [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md)및 [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata 가져오기 인터페이스에 전달할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8f6a9-109">The token can be passed to the [IMetaDataImport](../metadata/imetadataimport-interface.md), [IMetaDataImport2](../metadata/imetadataimport2-interface.md), and [IMetaDataAssemblyImport](../metadata/imetadataassemblyimport-interface.md) metadata import interfaces.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8f6a9-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8f6a9-110">Requirements</span></span>  

 <span data-ttu-id="8f6a9-111">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="8f6a9-111">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8f6a9-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8f6a9-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8f6a9-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8f6a9-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8f6a9-114">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8f6a9-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f6a9-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8f6a9-115">See also</span></span>

- [<span data-ttu-id="8f6a9-116">메타데이터</span><span class="sxs-lookup"><span data-stu-id="8f6a9-116">Metadata</span></span>](../metadata/index.md)
