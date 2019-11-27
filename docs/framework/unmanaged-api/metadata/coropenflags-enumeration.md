---
title: CorOpenFlags 열거형
ms.date: 03/30/2017
api_name:
- CorOpenFlags
api_location:
- mscoree.dll
api_type:
- COM
f1_keywords:
- CorOpenFlags
helpviewer_keywords:
- CorOpenFlags enumeration [.NET Framework metadata]
ms.assetid: e27a83b5-2698-4996-9032-1e0fed8b91ca
topic_type:
- apiref
ms.openlocfilehash: ad582fc2fd1bd1d2fc9d5a0d483fdb3a51309a10
ms.sourcegitcommit: 9a39f2a06f110c9c7ca54ba216900d038aa14ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/23/2019
ms.locfileid: "74436498"
---
# <a name="coropenflags-enumeration"></a>CorOpenFlags 열거형
매니페스트 파일을 열 때 메타데이터 동작을 제어하는 플래그 값을 포함합니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
typedef enum CorOpenFlags  
{  
    ofRead              =   0x00000000,  
    ofWrite             =   0x00000001,  
    ofReadWriteMask     =   0x00000001,  
    ofCopyMemory        =   0x00000002,  
    ofCacheImage        =   0x00000004,  
    ofManifestMetadata  =   0x00000008,  
    ofReadOnly          =   0x00000010,  
    ofTakeOwnership     =   0x00000020,  
    ofCacheImage        =   0x00000004,  
    ofNoTypeLib         =   0x00000080,  
    ofNoTransform       =   0x00001000,  
    ofReserved1         =   0x00000100,  
    ofReserved2         =   0x00000200,  
    ofReserved          =   0xffffff40  
} CorOpenFlags;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|설명|  
|------------|-----------------|  
|`ofRead`|파일을 읽기 전용으로 열어야 함을 나타냅니다.|  
|`ofWrite`|쓸 수 있도록 파일을 열어야 함을 나타냅니다.<br /><br /> .winmd 파일을 열 때 `ofWrite` 플래그를 사용하는 경우에는 `ofNoTransform` 플래그도 전달해야 합니다.|  
|`ofReadWriteMask`|읽기 및 쓰기용 마스크입니다.|  
|`ofCopyMemory`|파일을 메모리로 읽어들여야 함을 나타냅니다. 메타데이터는 자체 복사본을 유지해야 합니다.|  
|`ofCacheImage`|사용되지 않습니다. 이 플래그는 무시됩니다.|  
|`ofManifestMetadata`|사용되지 않습니다. 이 플래그는 무시됩니다.|  
|`ofReadOnly`|읽기 위해 파일을 열어야 하며 [IMetaDataEmit](../../../../docs/framework/unmanaged-api/metadata/imetadataemit-interface.md) 에 대 한 `QueryInterface` 호출을 만들 수 없음을 나타냅니다.|  
|`ofTakeOwnership`|메모리가 [CoTaskMemAlloc](/windows/desktop/api/combaseapi/nf-combaseapi-cotaskmemalloc) 에 대 한 호출을 사용 하 여 할당 되었으며 메타 데이터에 의해 해제 됨을 나타냅니다.|  
|`ofNoTypeLib`|사용되지 않습니다. 이 플래그는 무시됩니다.|  
|`ofNoTransform`|.winmd 파일의 자동 변형을 사용하지 않도록 설정해야 함을 나타냅니다. 즉, Windows 런타임 형식에서 .NET Framework 형식으로의 프로젝션을 사용하지 않도록 설정해야 합니다. 자세한 내용은 [Windows 런타임 및 CLR-.net 및 Windows 런타임의 내부](https://docs.microsoft.com/archive/msdn-magazine/2012/windows-8-special-issue/windows-runtime-and-the-clr-underneath-the-hood-with-net-and-the-windows-runtime)를 참조 하십시오.|  
|`ofReserved1`|내부 용도로 예약되어 있습니다.|  
|`ofReserved2`|내부 용도로 예약되어 있습니다.|  
|`ofReserved`|내부 용도로 예약되어 있습니다.|  
  
## <a name="requirements"></a>요구 사항  
 **플랫폼:** [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)을 참조하세요.  
  
 **헤더:** CorHdr .h  
  
 **.NET Framework 버전:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]  
  
## <a name="see-also"></a>참고 항목

- [메타데이터 열거형](../../../../docs/framework/unmanaged-api/metadata/metadata-enumerations.md)
