---
title: 'C# 예약된 특성: 호출자 정보 추적'
ms.date: 04/09/2020
description: 이 특성은 멤버를 호출하는 코드에 대한 정보를 생성하도록 컴파일러에 지시합니다. CallerFilePath, CallerLineNumber 및 CallerMemberName을 사용하여 자세한 추적 정보를 제공합니다.
ms.openlocfilehash: ee061d4cae35bdcc0b89007e360e94fee8c5f87c
ms.sourcegitcommit: c91110ef6ee3fedb591f3d628dc17739c4a7071e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/15/2020
ms.locfileid: "81389825"
---
# <a name="reserved-attributes-determine-caller-information"></a>예약된 특성: 호출자 정보 확인

정보 특성을 사용하여 메서드 호출자에 대한 정보를 가져옵니다. 소스 코드 파일 경로, 소스 코드 줄 번호 및 호출자의 멤버 이름을 가져옵니다. 멤버 호출자 정보를 얻으려면 선택적 매개 변수에 적용되는 특성을 사용합니다. 각 선택적 매개 변수는 기본값을 지정합니다. 다음 표에서는 <xref:System.Runtime.CompilerServices?displayProperty=nameWithType> 네임스페이스에 정의된 호출자 정보 특성을 보여줍니다.

|특성|설명|형식|
|---|---|---|
|<xref:System.Runtime.CompilerServices.CallerFilePathAttribute>|호출자를 포함한 소스 파일의 전체 경로입니다. 전체 경로는 컴파일 시간의 경로입니다.|`String`|
|<xref:System.Runtime.CompilerServices.CallerLineNumberAttribute>|메서드가 호출되는 소스 파일의 줄 번호입니다.|`Integer`|
|<xref:System.Runtime.CompilerServices.CallerMemberNameAttribute>|호출자의 메서드 이름 또는 속성 이름입니다.|`String`|

이 정보는 추적, 디버깅을 작성하고 진단 도구를 만드는 데 도움이 됩니다. 다음 예제에서는 호출자 정보 특성을 사용하는 방법을 보여 줍니다. `TraceMessage` 메서드에 대한 각 호출에서 호출자 정보는 선택적 매개 변수에 대한 인수로 대체됩니다.

```csharp
public void DoProcessing()
{
    TraceMessage("Something happened.");
}

public void TraceMessage(string message,
        [CallerMemberName] string memberName = "",
        [CallerFilePath] string sourceFilePath = "",
        [CallerLineNumber] int sourceLineNumber = 0)
{
    Trace.WriteLine("message: " + message);
    Trace.WriteLine("member name: " + memberName);
    Trace.WriteLine("source file path: " + sourceFilePath);
    Trace.WriteLine("source line number: " + sourceLineNumber);
}

// Sample Output:
//  message: Something happened.
//  member name: DoProcessing
//  source file path: c:\Visual Studio Projects\CallerInfoCS\CallerInfoCS\Form1.cs
//  source line number: 31
```

각각의 선택적 매개 변수에 대한 명시적 기본값을 지정합니다. 선택적 매개 변수로 지정되지 않은 매개 변수에 호출자 정보 특성을 적용할 수 없습니다. 호출자 정보 특성은 매개 변수를 선택적 매개 변수로 만들지 못합니다. 대신, 이런 특성은 인수가 생략될 때 전달되는 기본값에 영향을 미칩니다. 호출자 정보 값은 컴파일 시간에 리터럴로 중간 언어(IL) 내로 내보냅니다. 예외에 대한 <xref:System.Exception.StackTrace%2A> 속성의 결과와 달리 결과가 난독화의 영향을 받지 않습니다. 선택적 인수를 명시적으로 제공하여 호출자 정보를 제어하거나 호출자 정보를 숨길 수 있습니다.

### <a name="member-names"></a>멤버 이름

`CallerMemberName` 특성을 사용하여 멤버 이름을 호출된 메서드에 대한 `String` 인수로 지정하는 것을 피할 수 있습니다. 이 기술을 사용하여 **이름 바꾸기 리팩터링**이 `String` 값을 변경하지 못하는 문제를 피합니다. 이 이점은 다음 작업에 특히 유용합니다.

- 추적 및 진단 루틴 사용.
- 데이터를 바인딩할 때 <xref:System.ComponentModel.INotifyPropertyChanged> 인터페이스 구현. 이 인터페이스에서는 컨트롤에서 업데이트된 정보를 표시할 수 있도록 바운드 컨트롤의 속성이 변경되었음을 알리는 개체의 속성을 사용할 수 있습니다. `CallerMemberName` 특성이 없으면 속성 이름을 리터럴로 지정해야 합니다.

아래 차트는 `CallerMemberName` 특성을 사용할 때 반환되는 멤버 이름을 보여줍니다.

|호출 발생 범위|멤버 이름 결과|
|-|-|
|메서드, 속성 또는 이벤트|호출에서 시작한 메서드, 속성 또는 이벤트의 이름입니다.|
|생성자|".ctor" 문자열|
|정적 생성자|".cctor" 문자열|
|소멸자|"Finalize" 문자열|
|사용자 정의 연산자 또는 변환|멤버에 대해 생성되는 이름입니다(예: "op_Addition").|
|특성 생성자|특성이 적용되는 메서드 또는 속성의 이름입니다. 특성이 멤버 내에 있는 어떤 요소인 경우(예: 매개 변수, 반환 값 또는 제네릭 형식 매개 변수) 이 결과는 그 요소와 관련된 멤버의 이름입니다.|
|포함하는 멤버가 없음(예: 어셈블리 수준 또는 형식에 적용되는 특성)|선택적 매개 변수의 기본값입니다.|

## <a name="see-also"></a>참조

- [명명된 인수 및 선택적 인수](../../programming-guide/classes-and-structs/named-and-optional-arguments.md)
- <xref:System.Reflection>
- <xref:System.Attribute>
- [특성](../../../standard/attributes/index.md)
