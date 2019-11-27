---
title: AssemblyAttributesGoHereS
ms.date: 03/30/2017
api_name:
- System.Runtime.CompilerServices.AssemblyAttributesGoHereS
api_location:
- mscorlib.dll
api_type:
- Assembly
f1_keywords:
- AssemblyAttributesGoHereS
helpviewer_keywords:
- AssemblyAttributesGoHereS type
- Alink API, AssemblyAttributesGoHereS type
ms.assetid: 4e817f35-a2bc-4403-9e6f-f731e6b9fe23
topic_type:
- apiref
ms.openlocfilehash: 128268bab77c8be5dc809eaa6d2548fc34f13cbd
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74446611"
---
# <a name="assemblyattributesgoheres"></a>AssemblyAttributesGoHereS

ALink에서 사용자 지정 특성 정보를 저장하는 자리 표시자로 사용됩니다.

## <a name="syntax"></a>구문

```csharp
internal sealed class AssemblyAttributesGoHereS
```

## <a name="remarks"></a>설명

이 형식에 대한 참조는 소스에 어셈블리 사용자 지정 특성이 들어 있는 netmodule 내부에 포함될 수 있습니다. 이러한 유형에 대한 참조가 포함된 netmodule 하나 이상에서 어셈블리 매니페스트를 빌드할 때 ALink에서는 이들 참조에 연결된 정보를 사용하여 실제 사용자 지정 특성을 내보냅니다. 따라서 이 형식은 인스턴스화되지 않으며, 이에 대한 참조는 빌드 프로세스 부분으로만 사용되고 최종 어셈블리에서 도움이 되지 않습니다.

이 형식에 대한 참조는 보안과 관련이 있고 다양한 용도로 사용되지 않는 사용자 지정 특성을 나타냅니다.

이러한 형식은 .NET Framework 내에서 "내부"로 표시 되 고 <xref:System.Runtime.CompilerServices> 네임 스페이스에 있습니다.

## <a name="requirements"></a>요구 사항

mscorlib.dll

## <a name="see-also"></a>참고자료

- [AssemblyAttributesGoHere](assemblyattributesgohere.md)
- [AssemblyAttributesGoHereM](assemblyattributesgoherem.md)
- [AssemblyAttributesGoHereSM](assemblyattributesgoheresm.md)
