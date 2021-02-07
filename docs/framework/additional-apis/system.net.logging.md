---
description: '자세한 정보: 로깅 클래스'
title: Logging 클래스 (System.Net)
ms.date: 06/12/2020
ms.technology: dotnet-networking
topic_type:
- apiref
api_name:
- System.Net.Logging
- System.Net.Logging.Associate
- System.Net.Logging.Enter
- System.Net.Logging.Exception
- System.Net.Logging.Exit
- System.Net.Logging.get_Http
- System.Net.Logging.get_On
api_location:
- System.dll
api_type:
- Assembly
ms.openlocfilehash: 1ae3079ab21502ee3f5bf71db57f0695da9a8571
ms.sourcegitcommit: ddf7edb67715a5b9a45e3dd44536dabc153c1de0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/06/2021
ms.locfileid: "99726210"
---
# <a name="logging-class"></a>Logging 클래스

추적 로깅 기능을 제공 합니다.

```csharp
internal class Logging
```

> [!WARNING]
> 이 클래스는 내부 클래스 이며 코드에서 직접 사용할 수 없습니다.
>
> Microsoft는 어떤 경우에도 프로덕션 응용 프로그램에서이 클래스를 사용 하는 것을 지원 하지 않습니다.

## <a name="associate-method"></a>연결 방법

두 개체가 서로 연결 된 정보를 기록 합니다.

```csharp
internal static void Associate(TraceSource traceSource, object objA, object objB)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `objA` <xref:System.Object>

  와 연결할 개체 `objB` 입니다.

- `objB` <xref:System.Object>

  와 연결할 개체 `objA` 입니다.

## <a name="entertracesource-object-string-string-method"></a>Enter (TraceSource, object, string, string) 메서드

메서드에 대 한 로그를 기록 합니다.

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, string param)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `obj` <xref:System.Object>

  메서드가 호출 된 개체입니다.

- `method` <xref:System.String>

  입력 중인 메서드입니다.

- `param` <xref:System.String>

  메서드에 전달 된 매개 변수입니다.

## <a name="entertracesource-object-string-object-method"></a>Enter (TraceSource, object, string, object) 메서드

메서드에 대 한 로그를 기록 합니다.

```csharp
internal static void Enter(TraceSource traceSource, object obj, string method, object paramObject)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `obj` <xref:System.Object>

  메서드가 호출 된 개체입니다.

- `method` <xref:System.String>

  입력 중인 메서드입니다.

- `paramObject` <xref:System.Object>

  메서드에 전달 된 매개 변수입니다.

## <a name="entertracesource-string-string-string-method"></a>Enter (TraceSource, string, string, string) 메서드

메서드에 대 한 로그를 기록 합니다.

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, string param)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `obj` <xref:System.String>

  메서드가 호출 된 개체입니다.

- `method` <xref:System.String>

  입력 중인 메서드입니다.

- `param` <xref:System.String>

  메서드에 전달 된 매개 변수입니다.

## <a name="entertracesource-string-string-object-method"></a>Enter (TraceSource, string, string, object) 메서드

메서드에 대 한 로그를 기록 합니다.

```csharp
internal static void Enter(TraceSource traceSource, string obj, string method, object paramObject)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `obj` <xref:System.String>

  메서드가 호출 된 개체입니다.

- `method` <xref:System.String>

  입력 중인 메서드입니다.

- `paramObject` <xref:System.Object>

  메서드에 전달 된 매개 변수입니다.

## <a name="entertracesource-string-string-method"></a>Enter (TraceSource, string, string) 메서드

메서드에 대 한 로그를 기록 합니다.

```csharp
internal static void Enter(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `method` <xref:System.String>

  입력 중인 메서드입니다.

- `parameters` <xref:System.String>

  메서드에 전달 된 매개 변수입니다.

## <a name="entertracesource-string-method"></a>Enter (TraceSource, string) 메서드

메서드에 대 한 로그를 기록 합니다.

```csharp
internal static void Enter(TraceSource traceSource, string msg)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `msg` <xref:System.String>

  추적 소스에 기록할 입구 메시지입니다.

## <a name="exception-method"></a>Exception 메서드

예외를 기록 하 고 들여쓰기를 복원 합니다.

```csharp
internal static void Exception(TraceSource traceSource, object obj, string method, Exception e)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `obj` <xref:System.Object>

  예외를 throw 한 메서드가 호출 된 개체입니다.

- `method` <xref:System.String>

  예외를 throw 한 메서드입니다.

- `e` <xref:System.Exception>

  throw된 예외입니다.

## <a name="exittracesource-object-string-object-method"></a>Exit (TraceSource, object, string, object) 메서드

함수에서 로그를 종료 합니다.

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, object retObject)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `obj` <xref:System.Object>

  메서드가 호출 된 개체입니다.

- `method` <xref:System.String>

  종료 되는 메서드입니다.

- `retObject` <xref:System.Object>

  메서드가 반환 하는 값입니다.

## <a name="exittracesource-string-string-object-method"></a>Exit (TraceSource, string, string, object) 메서드

함수에서 로그를 종료 합니다.

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, object retObject)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `obj` <xref:System.String>

  메서드가 호출 된 개체입니다.

- `method` <xref:System.String>

  종료 되는 메서드입니다.

- `retObject` <xref:System.Object>

  메서드가 반환 하는 값입니다.

## <a name="exittracesource-object-string-string-method"></a>Exit (TraceSource, object, string, string) 메서드

함수에서 로그를 종료 합니다.

```csharp
internal static void Exit(TraceSource traceSource, object obj, string method, string retValue)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `obj` <xref:System.Object>

  메서드가 호출 된 개체입니다.

- `method` <xref:System.String>

  종료 되는 메서드입니다.

- `retValue` <xref:System.String>

  메서드가 반환 하는 값입니다.

## <a name="exittracesource-string-string-string-method"></a>Exit (TraceSource, string, string, string) 메서드

함수에서 로그를 종료 합니다.

```csharp
internal static void Exit(TraceSource traceSource, string obj, string method, string retValue)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `obj` <xref:System.String>

  메서드가 호출 된 개체입니다.

- `method` <xref:System.String>

  종료 되는 메서드입니다.

- `retValue` <xref:System.String>

  메서드가 반환 하는 값입니다.

## <a name="exittracesource-string-string-method"></a>Exit (TraceSource, string, string) 메서드

함수에서 로그를 종료 합니다.

```csharp
internal static void Exit(TraceSource traceSource, string method, string parameters)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `method` <xref:System.String>

  종료 되는 메서드입니다.

- `parameters` <xref:System.String>

  종료 되는 메서드에 전달 된 매개 변수입니다.

## <a name="exittracesource-string-method"></a>Exit (TraceSource, string) 메서드

함수에서 로그를 종료 합니다.

```csharp
internal static void Exit(TraceSource traceSource, string msg)
```

### <a name="parameters"></a>매개 변수

- `traceSource` <xref:System.Diagnostics.TraceSource>

  이벤트를 로깅할 추적 소스입니다.

- `msg` <xref:System.String>

  추적 소스에 기록할 종료 메시지입니다.

## <a name="http-property"></a>Http 속성

"System .Net. Http"의 추적 소스를 가져옵니다.

```csharp
internal static TraceSource Http { get; }
```

### <a name="property-value"></a>속성 값

<xref:System.Diagnostics.TraceSource>\
"System .Net. Http"의 추적 소스 이거나, `null` 로깅을 사용할 수 없으면입니다.

## <a name="on-property"></a>On 속성

로깅을 사용할 수 있는지 여부를 나타내는 값을 가져옵니다.

```csharp
internal static bool On { get; }
```

### <a name="property-value"></a>속성 값

<xref:System.Boolean>\
로깅을 사용할 수 있으면 `true`이고, 그렇지 않으면 `false`입니다.

## <a name="requirements"></a>요구 사항

**네임스페이스:** <xref:System.Net>

**어셈블리:** 시스템 (System.dll)
