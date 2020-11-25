---
title: ICorDebugEval2::NewParameterizedObject 메서드
ms.date: 03/30/2017
api_name:
- ICorDebugEval2.NewParameterizedObject
api_location:
- mscordbi.dll
api_type:
- COM
f1_keywords:
- ICorDebugEval2::NewParameterizedObject
helpviewer_keywords:
- NewParameterizedObject method [.NET Framework debugging]
- ICorDebugEval2::NewParameterizedObject method [.NET Framework debugging]
ms.assetid: 3d705463-e640-4249-8036-4e8206d03cfe
topic_type:
- apiref
ms.openlocfilehash: 8c91296bd4185fd98962d49f611a3cdcb5f0ad28
ms.sourcegitcommit: d8020797a6657d0fbbdff362b80300815f682f94
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/24/2020
ms.locfileid: "95729662"
---
# <a name="icordebugeval2newparameterizedobject-method"></a><span data-ttu-id="aedb0-102">ICorDebugEval2::NewParameterizedObject 메서드</span><span class="sxs-lookup"><span data-stu-id="aedb0-102">ICorDebugEval2::NewParameterizedObject Method</span></span>

<span data-ttu-id="aedb0-103">매개 변수가 있는 새 형식 개체를 인스턴스화하고 개체의 생성자 메서드를 호출 합니다.</span><span class="sxs-lookup"><span data-stu-id="aedb0-103">Instantiates a new parameterized type object and calls the object's constructor method.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="aedb0-104">구문</span><span class="sxs-lookup"><span data-stu-id="aedb0-104">Syntax</span></span>  
  
```cpp  
HRESULT NewParameterizedObject (  
    [in] ICorDebugFunction     *pConstructor,  
    [in] ULONG32               nTypeArgs,  
    [in, size_is(nTypeArgs)] ICorDebugType *ppTypeArgs[],  
    [in] ULONG32               nArgs,  
    [in, size_is(nArgs)] ICorDebugValue *ppArgs[]  
);  
```  
  
## <a name="parameters"></a><span data-ttu-id="aedb0-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="aedb0-105">Parameters</span></span>  

 `pConstructor`  
 <span data-ttu-id="aedb0-106">진행 인스턴스화할 개체의 생성자를 나타내는 ICorDebugFunction 개체에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="aedb0-106">[in] A pointer to an ICorDebugFunction object that represents the constructor of the object to be instantiated.</span></span>  
  
 `nTypeArgs`  
 <span data-ttu-id="aedb0-107">진행 전달 된 형식 인수의 수입니다.</span><span class="sxs-lookup"><span data-stu-id="aedb0-107">[in] The number of type arguments passed.</span></span>  
  
 `ppTypeArgs`  
 <span data-ttu-id="aedb0-108">진행 각각 인스턴스화되는 개체에 대 한 형식 인수를 나타내는 ICorDebugType 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="aedb0-108">[in] An array of pointers, each of which points to an ICorDebugType object that represents a type argument for the object that is being instantiated.</span></span>  
  
 `nArgs`  
 <span data-ttu-id="aedb0-109">진행 생성자에 전달 되는 인수 수입니다.</span><span class="sxs-lookup"><span data-stu-id="aedb0-109">[in] The number of arguments passed to the constructor.</span></span>  
  
 `ppArgs`  
 <span data-ttu-id="aedb0-110">진행 각각 생성자에 전달 되는 인수 값을 나타내는 ICorDebugValue 개체를 가리키는 포인터의 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="aedb0-110">[in] An array of pointers, each of which points to an ICorDebugValue object that represents an argument value that is passed to the constructor.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="aedb0-111">설명</span><span class="sxs-lookup"><span data-stu-id="aedb0-111">Remarks</span></span>  

 <span data-ttu-id="aedb0-112">개체의 생성자는 매개 변수를 사용할 수 있습니다 <xref:System.Type> .</span><span class="sxs-lookup"><span data-stu-id="aedb0-112">The object's constructor may take <xref:System.Type> parameters.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="aedb0-113">요구 사항</span><span class="sxs-lookup"><span data-stu-id="aedb0-113">Requirements</span></span>  

 <span data-ttu-id="aedb0-114">**플랫폼:**[시스템 요구 사항](../../get-started/system-requirements.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="aedb0-114">**Platforms:** See [System Requirements](../../get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="aedb0-115">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="aedb0-115">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="aedb0-116">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="aedb0-116">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="aedb0-117">**.NET Framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="aedb0-117">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>
