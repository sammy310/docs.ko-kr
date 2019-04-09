---
title: 약한 이벤트 패턴
ms.date: 03/30/2017
helpviewer_keywords:
- weak event pattern implementation [WPF]
- event handlers [WPF], weak event pattern
- IWeakEventListener interface [WPF]
ms.assetid: e7c62920-4812-4811-94d8-050a65c856f6
ms.openlocfilehash: 49795235d489ebc70cec11332e6be4a9452bc21d
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139258"
---
# <a name="weak-event-patterns"></a>약한 이벤트 패턴
응용 프로그램에서 있기 이벤트 소스에 연결 된 처리기를 조정 하 여 원본에 처리기를 연결 하는 수신기 개체를 사용 하 여 소멸 되지 것입니다. 이 경우 메모리 누수가 발생할 수 있습니다. [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 특정 이벤트에 대 한 전용된 관리자 클래스를 제공 하 고 해당 이벤트에 대 한 수신기에서 인터페이스를 구현 하 여이 문제를 해결 하기 위해 사용할 수 있는 디자인 패턴을 소개 합니다. 이 디자인 패턴 이라고 합니다 *약한 이벤트 패턴*합니다.  
  
## <a name="why-implement-the-weak-event-pattern"></a>약한 이벤트 패턴을 구현 하는 이유  
 이벤트를 수신 대기 메모리 누수가 발생할 수 있습니다. 이벤트를 수신 하는 일반적인 방법은 원본에서 이벤트 처리기를 연결 하는 언어별 구문을 사용 하는 것입니다. 예를 들어, C#에 구문은: `source.SomeEvent += new SomeEventHandler(MyEventHandler)`합니다.  
  
 이 기술은 이벤트 수신기에 이벤트 원본에서 강력한 참조를 만듭니다. 일반적으로 수신기에 대 한 이벤트 처리기를 연결 하면 해당 수신기 개체 수명이 원본의 개체 수명에 영향을 받습니다 (하지 않는 한 이벤트 처리기가 명시적으로 제거)입니다. 하지만 속해 있는지 여부 현재 응용 프로그램 및 원본의 수명을가 아닌 시각적 트리 같은 개체 수명의 수신기에 대 한 다른 요인에 의해 제어 하려는 경우에 따라 있습니다. 일반적인 이벤트 패턴 메모리 누수를 발생 시키는 소스 개체 수명을 수신기의 개체 수명을 넘어가는, 때마다: 수신기 것 보다 더 이상 활성 상태로 유지 됩니다.  
  
 약한 이벤트 패턴에는이 메모리 누수 문제를 해결 하도록 설계 되었습니다. 수신기가 이벤트를 등록 해야 하지만 수신기를 명시적으로 알지 등록을 취소 하는 경우 때마다 약한 이벤트 패턴을 사용할 수 있습니다. 수신기의 유용한 개체 수명을 초과 하는 원본의 개체 수명을 때마다 약한 이벤트 패턴에도 사용할 수 있습니다. (이 예에서 *유용* 사용자에 의해 결정 됩니다.) 약한 이벤트 패턴에 수신기를를 등록 하 고 어떤 방식으로든에서 수신기의 개체 수명 특성을 영향을 주지 않고 이벤트를 수신할 수 있습니다. 실제로 소스에서 대 한 암시적된 참조가 수신기가 가비지 수집 대상이 있는지을 확인 하지 않습니다. 참조는 약한 참조 하므로 명명 약한 이벤트 패턴 및 관련 [!INCLUDE[TLA2#tla_api#plural](../../../../includes/tla2sharptla-apisharpplural-md.md)]합니다. 수신기 가비지 수집 또는 그렇지 않은 경우 제거 되며 원본 존재할 삭제 된 개체에 대 한 처리기 참조를 유지 하지 않고 계속할 수 있습니다.  
  
## <a name="who-should-implement-the-weak-event-pattern"></a>약한 이벤트 패턴을 구현 해야 하는  
 약한 이벤트 패턴을 구현 하는 것은 주로 컨트롤 작성자를 위한 흥미로운 합니다. 컨트롤 작성자 담당 주로 동작을 컨트롤에서 삽입 되는 응용 프로그램에 영향을 포함 합니다. 여기에 컨트롤 개체 수명 동작, 특히 설명한 메모리 누수 문제를 처리 합니다.  
  
 특정 시나리오 기본적으로 자체적으로 약한 이벤트 패턴을 적용 합니다. 이러한 시나리오 중 하나는 데이터 바인딩입니다. 이 데이터 바인딩에서 바인딩 대상 수신기 개체를 완전히 독립 소스 개체에 대 한 일반적입니다. 여러 가지 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] 약한 이벤트 패턴의 이벤트 구현 방식에서 적용 한 데이터 바인딩이 이미 있습니다.  
  
## <a name="how-to-implement-the-weak-event-pattern"></a>약한 이벤트 패턴을 구현 하는 방법  
 약한 이벤트 패턴을 구현 하는 방법은 세 가지가 있습니다. 다음 표에서 세 가지 방법을 나열 하 고 각 사용 시기에 대 한 몇 가지 지침을 제공 합니다.  
  
|방식|구현 하는 경우|  
|--------------|-----------------------|  
|기존 강력 하지 않은 이벤트 관리자 클래스를 사용 합니다.|구독 하려는 이벤트에 해당 하는 경우 <xref:System.Windows.WeakEventManager>, 기존 강력 하지 않은 이벤트 관리자를 사용 합니다. WPF와 함께 제공 되는 약한 이벤트 관리자의 목록, 참조의 상속 계층 구조는 <xref:System.Windows.WeakEventManager> 클래스입니다. 포함 된 약한 이벤트 관리자 제한 되므로, 아마도 다른 방법 중 하나를 선택 해야 합니다.|  
|제네릭 약한 이벤트 관리자 클래스를 사용 하 여|제네릭 사용 <xref:System.Windows.WeakEventManager%602> 기존 <xref:System.Windows.WeakEventManager> 를 사용할 수 없는 구현 하는 간편한 방법은 원하는 및 없는 관련이 효율성에 대 한 합니다. 제네릭 <xref:System.Windows.WeakEventManager%602> 약한 이벤트 관리자를 기존 또는 사용자 지정 보다 덜 효율적입니다. 예를 들어, 제네릭 클래스는 이벤트의 이름이 지정 된 이벤트를 검색 하기 위해 자세한 리플렉션을 수행 합니다. 제네릭 사용 하 여 이벤트를 등록 하는 코드 또한 <xref:System.Windows.WeakEventManager%602> 더 기존를 사용 하 여 보다 자세한 정보 또는 사용자 지정 <xref:System.Windows.WeakEventManager>합니다.|  
|사용자 지정 약한 이벤트 관리자 클래스를 만듭니다|사용자 지정 만들기 <xref:System.Windows.WeakEventManager> 기존 <xref:System.Windows.WeakEventManager> 사용할 수 없는 효율성을 극대화 하려는 합니다. 사용자 지정을 사용 하 여 <xref:System.Windows.WeakEventManager> 구독할 이벤트 보다 효율적 이지만 시작 부분에 더 많은 코드를 작성 하는 비용이 수행할 수 있습니다.|  
|타사 약한 이벤트 관리자를 사용 하 여|NuGet은 [여러 약한 이벤트 관리자](https://www.nuget.org/packages?q=weak+event+manager&prerel=false) 많은 WPF 프레임 워크는 또한 패턴을 지원 하 고 (예를 들어 참조 [느슨하게 연결 된 이벤트 구독에 대 한 Prism의 설명서](https://github.com/PrismLibrary/Prism-Documentation/blob/master/docs/wpf/Communication.md#subscribing-to-events)).|

 다음 섹션에서는 약한 이벤트 패턴을 구현 하는 방법에 설명 합니다.  이 토론을 위해 이벤트를 구독할 다음과 같은 특징이 있습니다.  
  
-   이벤트 이름은 `SomeEvent`합니다.  
  
-   이벤트가 발생 합니다 `EventSource` 클래스입니다.  
  
-   이벤트 처리기의 형식: `SomeEventEventHandler` (또는 `EventHandler<SomeEventEventArgs>`).  
  
-   형식의 매개 변수를 전달 하는 이벤트 `SomeEventEventArgs` 이벤트 처리기에 있습니다.  
  
### <a name="using-an-existing-weak-event-manager-class"></a>기존 강력 하지 않은 이벤트 관리자 클래스를 사용 하 여  
  
1.  관리자를 기존 약한 이벤트를 찾습니다.  
  
     WPF와 함께 제공 되는 약한 이벤트 관리자의 목록, 참조의 상속 계층 구조는 <xref:System.Windows.WeakEventManager> 클래스입니다.  
  
2.  일반 이벤트를 후크 하는 대신 새로운 약한 이벤트 관리자를 사용 합니다.  
  
     예를 들어 다음과 같이 코드 패턴을 사용 하 여 이벤트를 구독할 수 있습니다.  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     다음 패턴으로 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     마찬가지로 코드에서 이벤트를 구독 취소 패턴을 사용 합니다.  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     다음 패턴으로 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
### <a name="using-the-generic-weak-event-manager-class"></a>제네릭 약한 이벤트 관리자 클래스를 사용 하 여  
  
1.  제네릭 사용 <xref:System.Windows.WeakEventManager%602> 일반 이벤트를 후크 하는 대신 클래스입니다.  
  
     사용 하는 경우 <xref:System.Windows.WeakEventManager%602> 이벤트 수신기를 등록 이벤트 소스를 제공 하 고 <xref:System.EventArgs> 클래스 및 호출 형식 매개 변수 형식과 <xref:System.Windows.WeakEventManager%602.AddHandler%2A> 다음 코드 에서처럼:  
  
    ```  
    WeakEventManager<EventSource, SomeEventEventArgs>.AddHandler(source, "SomeEvent", source_SomeEvent);  
    ```  
  
### <a name="creating-a-custom-weak-event-manager-class"></a>약한 이벤트 관리자 클래스를 사용자 지정 만들기  
  
1.  다음 클래스 템플릿을 프로젝트에 복사 합니다.  
  
     이 클래스에서 상속 된 <xref:System.Windows.WeakEventManager> 클래스입니다.  
  
     [!code-csharp[WeakEvents#WeakEventManagerTemplate](~/samples/snippets/csharp/VS_Snippets_Wpf/WeakEvents/CSharp/WeakEventManagerTemplate.cs#weakeventmanagertemplate)]  
  
2.  대체는 `SomeEventWeakEventManager` 고유한 이름의 이름입니다.  
  
3.  이벤트에 대 한 해당 이름의 앞에서 설명한 3 개의 이름을 대체 합니다. (`SomeEvent`하십시오 `EventSource`, 및 `SomeEventEventArgs`)  
  
4.  관리 이벤트로 동일한 표시 약한 이벤트 관리자 클래스의 표시 여부 (공개 / 개인, 내부)을 설정 합니다.  
  
5.  일반 이벤트를 후크 하는 대신 새로운 약한 이벤트 관리자를 사용 합니다.  
  
     예를 들어 다음과 같이 코드 패턴을 사용 하 여 이벤트를 구독할 수 있습니다.  
  
    ```  
    source.SomeEvent += new SomeEventEventHandler(OnSomeEvent);  
    ```  
  
     다음 패턴으로 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.AddHandler(source, OnSomeEvent);  
    ```  
  
     마찬가지로 코드에서 이벤트를 구독 취소 패턴을 사용 합니다.  
  
    ```  
    source.SomeEvent -= new SomeEventEventHandler(OnSome);  
    ```  
  
     다음 패턴으로 변경 합니다.  
  
    ```  
    SomeEventWeakEventManager.RemoveHandler(source, OnSomeEvent);  
    ```  
  
## <a name="see-also"></a>참고자료

- <xref:System.Windows.WeakEventManager>
- <xref:System.Windows.IWeakEventListener>
- [라우트된 이벤트 개요](routed-events-overview.md)
- [데이터 바인딩 개요](../data/data-binding-overview.md)
