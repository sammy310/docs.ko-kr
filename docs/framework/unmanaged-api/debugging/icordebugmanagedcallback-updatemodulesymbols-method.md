---
description: '자세히 알아보기: ICorDebugManagedCallback:: UpdateModuleSymbols 메서드'
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
ms.openlocfilehash: 1e20ee50cdbe0b36d0677051f1fe2b1c777e6cd6
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99790934"
---
# <a name="icordebugmanagedcallbackupdatemodulesymbols-method"></a><span data-ttu-id="a7d4e-103">ICorDebugManagedCallback::UpdateModuleSymbols 메서드</span><span class="sxs-lookup"><span data-stu-id="a7d4e-103">ICorDebugManagedCallback::UpdateModuleSymbols Method</span></span>

<span data-ttu-id="a7d4e-104">공용 언어 런타임 모듈의 기호가 변경 되었음을 디버거에 알립니다.</span><span class="sxs-lookup"><span data-stu-id="a7d4e-104">Notifies the debugger that the symbols for a common language runtime module have changed.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a7d4e-105">구문</span><span class="sxs-lookup"><span data-stu-id="a7d4e-105">Syntax</span></span>  
  
```cpp  
HRESULT UpdateModuleSymbols (  
    [in] ICorDebugAppDomain *pAppDomain,  
    [in] ICorDebugModule    *pModule,  
    [in] IStream            *pSymbolStream  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="a7d4e-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="a7d4e-106">Parameters</span></span>  

 `pAppDomain`  
 <span data-ttu-id="a7d4e-107">진행 기호가 변경 된 모듈이 포함 된 응용 프로그램 도메인을 나타내는 ICorDebugAppDomain 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a7d4e-107">[in] A pointer to an ICorDebugAppDomain object that represents the application domain containing the module in which the symbols have changed.</span></span>  
  
 `pModule`  
 <span data-ttu-id="a7d4e-108">진행 기호가 변경 된 모듈을 나타내는 ICorDebugModule 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a7d4e-108">[in] A pointer to an ICorDebugModule object that represents the module in which the symbols have changed.</span></span>  
  
 `pSymbolStream`  
 <span data-ttu-id="a7d4e-109">진행 `IStream` 수정 된 기호를 포함 하는 WIN32 COM 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="a7d4e-109">[in] A pointer to a Win32 COM `IStream` object that contains the modified symbols.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="a7d4e-110">설명</span><span class="sxs-lookup"><span data-stu-id="a7d4e-110">Remarks</span></span>  

 <span data-ttu-id="a7d4e-111">이 메서드는 [ISymUnmanagedReader:: UpdateSymbolStore](../diagnostics/isymunmanagedreader-updatesymbolstore-method.md) 또는 [ISymUnmanagedReader:: ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md)를 호출 하 여 모듈 기호의 디버거 뷰를 업데이트할 수 있는 기회를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7d4e-111">This method provides an opportunity to update the debugger's view of a module's symbols by calling [ISymUnmanagedReader::UpdateSymbolStore](../diagnostics/isymunmanagedreader-updatesymbolstore-method.md) or [ISymUnmanagedReader::ReplaceSymbolStore](../diagnostics/isymunmanagedreader-replacesymbolstore-method.md).</span></span>  
  
 <span data-ttu-id="a7d4e-112">이 콜백은 동일한 모듈에 대해 여러 번 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="a7d4e-112">This callback can occur multiple times for the same module.</span></span>  
  
 <span data-ttu-id="a7d4e-113">디버거는 바인딩되지 않은 소스 수준 중단점을 바인딩해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="a7d4e-113">A debugger should try to bind unbound source-level breakpoints.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="a7d4e-114">요구 사항</span><span class="sxs-lookup"><span data-stu-id="a7d4e-114">Requirements</span></span>  

 <span data-ttu-id="a7d4e-115">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="a7d4e-115">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="a7d4e-116">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="a7d4e-116">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="a7d4e-117">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="a7d4e-117">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="a7d4e-118">**.NET Framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="a7d4e-118">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a7d4e-119">참고 항목</span><span class="sxs-lookup"><span data-stu-id="a7d4e-119">See also</span></span>

- [<span data-ttu-id="a7d4e-120">ICorDebugManagedCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="a7d4e-120">ICorDebugManagedCallback Interface</span></span>](icordebugmanagedcallback-interface.md)
