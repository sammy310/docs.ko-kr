---
title: ICorDebugManagedCallback::UpdateModuleSymbols 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugManagedCallback.UpdateModuleSymbols
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugManagedCallback::UpdateModuleSymbols
helpviewer_keywords:
- UpdateModuleSymbols method [.NET Framework debugging]
- ICorDebugManagedCallback::UpdateModuleSymbols method [.NET Framework debugging]
ms.assetid: 0863f644-58e8-45a0-b0c3-a28e99b20938
topic_type:
- apiref
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 581ea4f974bfec3961a32cd7c9985a5e45d2bddd
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61995074"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="f0f75-102">ICorDebugManagedCallback::UpdateModuleSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="f0f75-102">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>
<span data-ttu-id="f0f75-103">공용 언어 런타임 모듈에 대 한 기호 변경 된 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="f0f75-103">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="f0f75-104">구문</span><span class="sxs-lookup"><span data-stu-id="f0f75-104">Syntax</span></span>  
  
```  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="f0f75-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="f0f75-105">Parameters</span></span>  
 `pAppDomain`  
 <span data-ttu-id="f0f75-106">[in] 기호 변경한 모듈을 포함 하는 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f75-106">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="f0f75-107">[in] 모듈의 기호가 변경 되었음을 나타내는 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f75-107">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="f0f75-108">[in] Win32 COM에 대 한 포인터 `IStream` 수정된 기호를 포함 하는 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="f0f75-108">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="f0f75-109">설명</span><span class="sxs-lookup"><span data-stu-id="f0f75-109">Remarks</span></span>  
 <span data-ttu-id="f0f75-110">이 메서드를 호출 하 여 모듈의 기호 디버거의 보기를 업데이트 하려면 기회가 [isymunmanagedreader:: Updatesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) 하거나 [isymunmanagedreader:: Replacesymbolstore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f75-110">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../../../../docs/framework/unmanaged-api/diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="f0f75-111">이 콜백은 같은 모듈에 대 한 여러 번 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f0f75-111">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="f0f75-112">디버거는 바인딩되지 않은 소스 수준 중단점을 바인딩할 시도해 야 합니다.</span><span class="sxs-lookup"><span data-stu-id="f0f75-112">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="f0f75-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="f0f75-113">Requirements</span></span>  
 <span data-ttu-id="f0f75-114">**플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="f0f75-114">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="f0f75-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="f0f75-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="f0f75-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="f0f75-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="f0f75-117">**.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="f0f75-117">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f0f75-118">참고자료</span><span class="sxs-lookup"><span data-stu-id="f0f75-118">See also</span></span>

- [<span data-ttu-id="f0f75-119">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="f0f75-119">ICorDebugManagedCallback Interface</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmanagedcallback-interface.md)
