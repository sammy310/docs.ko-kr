---
title: WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) 메서드
ms.date: 03/30/2017
ms.technology: dotnet-standard
dev_langs:
- csharp
- vb
api_name:
- System.IO.WindowsRuntimeStreamExtensions.AsRandomAccessStream
api_location:
- System.Runtime.WindowsRuntime.dll
ms.assetid: dcc72283-caed-49ee-b45d-ccaf94e97129
author: mairaw
ms.author: mairaw
ms.openlocfilehash: d5dd2829a9a00f869af3d7f370f99361979b8106
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61921318"
---
# <a name="windowsruntimestreamextensionsasrandomaccessstreamsystemiostream-method"></a>WindowsRuntimeStreamExtensions.AsRandomAccessStream(System.IO.Stream) 메서드

[.NET Framework 4.5.1 이상 버전에서 지원됨]

지정된 스트림을 임의 액세스 스트림으로 변환합니다.

**네임스페이스:** <xref:System.IO?displayProperty=nameWithType>
**어셈블리:** System.Runtime.WindowsRuntime (in System.Runtime.WindowsRuntime.dll)

## <a name="syntax"></a>구문

```csharp
[CLSCompliantAttribute(false)]
public static IRandomAccessStream AsRandomAccessStream(Stream stream)
```

```vb
'Declaration
<ExtensionAttribute> _
<CLSCompliantAttribute(False)> _
Public Shared Function AsRandomAccessStream ( _
        stream As Stream) As IRandomAccessStream
```

## <a name="parameters"></a>매개 변수

`stream`

형식: <xref:System.IO.Stream?displayProperty=nameWithType>  
변환할 스트림입니다.

## <a name="return-value"></a>반환 값

형식: <xref:Windows.Storage.Streams.RandomAccessStream>  
[!INCLUDE[wrt](../../../includes/wrt-md.md)] 임의 액세스 스트림은 변환된 된 스트림을 나타냅니다.

## <a name="exceptions"></a>예외

|예외|조건|
|---------------|---------------|
|<xref:System.NotSupportedException>|변환할 스트림은 검색을 지원하지 않습니다.|

## <a name="remarks"></a>설명

이 확장명 메서드는 Windows 스토어 앱을 개발하는 경우에만 사용할 수 있습니다. 이 메서드는 Windows 스토어 앱의 스트림을 작업하는 데 편리를 제공합니다. 변환하려는 .NET Framework 스트림은 검색을 지원해야 합니다. 자세한 내용은 <xref:System.IO.Stream.Seek%2A?displayProperty=nameWithType> 메서드를 참조하세요.

> [!IMPORTANT]
> 이 API는 .NET Framework 4.5.1 이상 버전에서 지원되지만 4.5 버전에서는 지원되지 않습니다.

## <a name="version-information"></a>버전 정보

**Windows 스토어 앱 용.NET**

지원 버전: Windows 8.1

## <a name="see-also"></a>참고자료

- [방법: .NET Framework 스트림과 Windows 런타임 스트림 간 변환](../io/how-to-convert-between-dotnet-streams-and-winrt-streams.md)
