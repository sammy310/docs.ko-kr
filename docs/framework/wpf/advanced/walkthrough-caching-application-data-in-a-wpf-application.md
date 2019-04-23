---
title: '연습: WPF 애플리케이션에서 애플리케이션 데이터 캐싱'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- walkthroughs [WPF], caching
- caching [.NET Framework]
- caching [WPF]
ms.assetid: dac2c9ce-042b-4d23-91eb-28f584415cef
ms.openlocfilehash: 1d00c222dabf446c7c102307c3b904d3f1ff4bca
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/18/2019
ms.locfileid: "59314398"
---
# <a name="walkthrough-caching-application-data-in-a-wpf-application"></a>연습: WPF 애플리케이션에서 애플리케이션 데이터 캐싱
캐싱을 사용하면 빠른 액세스를 위해 데이터를 메모리에 저장할 수 있습니다. 데이터에 다시 액세스할 때 애플리케이션은 원래 소스에서 검색하는 대신 캐시에서 데이터를 가져올 수 있습니다. 이 경우 성능과 확장성이 향상됩니다. 또한 캐싱을 사용하면 데이터 소스를 일시적으로 사용할 수 없는 경우에도 데이터를 사용할 수 있습니다.

 합니다 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 에서 캐싱을 사용할 수 있도록 하는 클래스를 제공 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램입니다. 이러한 클래스에는 <xref:System.Runtime.Caching> 네임 스페이스입니다.

> [!NOTE]
>  합니다 <xref:System.Runtime.Caching> 네임 스페이스의 새로운는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다. 이 네임 스페이스는 모든 사용 가능한 캐싱은 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 응용 프로그램입니다. 이전 버전의 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)]에서는 캐싱을 <xref:System.Web> 네임스페이스에서만 사용할 수 있었기 때문에 ASP.NET 클래스에 대한 종속성이 필요했습니다.

 이 연습에서 사용할 수 있는 캐싱 기능을 사용 하는 방법을 보여 줍니다.는 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] 의 일부로 [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] 응용 프로그램입니다. 이 연습에서는 텍스트 파일의 내용을 캐시 합니다.

 이 연습에서 수행할 작업은 다음과 같습니다.

-   WPF 응용 프로그램 프로젝트를 만드는 중입니다.

-   에 대 한 참조를 추가 합니다 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다.

-   캐시를 초기화합니다.

-   텍스트 파일의 내용을 포함 하는 캐시 항목을 추가 합니다.

-   캐시 엔트리에 대 한 제거 정책을 제공합니다.

-   캐시 된 파일의 경로 모니터링 하 고 캐시 인스턴스에 대 한 알림 모니터링된 항목을 변경 합니다.

## <a name="prerequisites"></a>전제 조건
 이 연습을 완료하려면 다음 사항이 필요합니다.

-   Microsoft Visual Studio 2010

-   적은 양의 텍스트를 포함 하는 텍스트 파일입니다. (텍스트 파일의 내용을 메시지 상자에 표시 됩니다.) 이 연습에 제공 된 코드를 사용 하는 다음 파일을 가정 합니다.

     `c:\cache\cacheText.txt`

     그러나 모든 텍스트 파일을 사용할 수 있으며이 연습에서는 코드를 약간 변경.

## <a name="creating-a-wpf-application-project"></a>WPF 응용 프로그램 프로젝트 만들기
 WPF 응용 프로그램 프로젝트를 만들어 시작 합니다.

#### <a name="to-create-a-wpf-application"></a>WPF 응용 프로그램을 만들려면

1. Visual Studio를 시작합니다.

2. 에 **파일** 메뉴에서 클릭 **새로 만들기**를 클릭 하 고 **새 프로젝트**합니다.

     **새 프로젝트** 대화 상자가 표시됩니다.

3. 아래 **설치 된 템플릿**를 사용 하려는 프로그래밍 언어 선택 (**Visual Basic** 또는 **Visual C#**).

4. 에 **새 프로젝트** 대화 상자에서 **WPF 응용 프로그램**합니다.

    > [!NOTE]
    >  표시 되지 않으면 합니다 **WPF 응용 프로그램** 템플릿을 버전을 대상으로 하는 있는지 확인 합니다 [!INCLUDE[dnprdnshort](../../../../includes/dnprdnshort-md.md)] WPF를 지 원하는. 에 **새 프로젝트** 대화 상자에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] 목록에서.

5. 에 **이름을** 텍스트 상자에 프로젝트의 이름을 입력 합니다. 예를 들어 입력할 수 있습니다 **WPFCaching**합니다.

6. **솔루션용 디렉터리 만들기** 확인란을 선택합니다.

7. **확인**을 클릭합니다.

     WPF 디자이너에서 엽니다 **디자인** 살펴보고 MainWindow.xaml 파일을 표시 합니다. Visual Studio 만듭니다는 **My Project** 폴더, Application.xaml 파일 및 MainWindow.xaml 파일입니다.

## <a name="targeting-the-net-framework-and-adding-a-reference-to-the-caching-assemblies"></a>.NET Framework 대상 지정 및 캐싱 어셈블리에 대 한 참조를 추가 합니다.
 기본적으로 WPF 응용 프로그램 대상의 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]합니다. 사용 하는 <xref:System.Runtime.Caching> WPF 응용 프로그램에서 네임 스페이스를 응용 프로그램 대상으로 해야 합니다는 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)] (하지는 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)]) 네임 스페이스에 대 한 참조를 포함 해야 합니다.

 따라서 다음 단계에 대 한 참조를 추가한.NET Framework 대상을 변경 하는 것은 <xref:System.Runtime.Caching> 네임 스페이스입니다.

> [!NOTE]
>  Visual C# 프로젝트에 Visual Basic 프로젝트에서 대상.NET 프레임 워크를 변경 하는 절차가 다릅니다.

#### <a name="to-change-the-target-net-framework-in-visual-basic"></a>Visual Basic에서.NET Framework 대상을 변경 하려면

1. **솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.

     응용 프로그램에 대 한 속성 창이 표시 됩니다.

2. **컴파일** 탭을 클릭합니다.

3. 창의 맨 아래에서 클릭 **고급 컴파일 옵션...** .

     합니다 **고급 컴파일러 설정** 대화 상자가 표시 됩니다.

4. 에 **대상 프레임 워크 (모든 구성)** 목록에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다. (선택 하지 않으면 [!INCLUDE[net_client_v40_long](../../../../includes/net-client-v40-long-md.md)].)

5. **확인**을 클릭합니다.

     **대상 프레임워크 변경** 대화 상자가 표시됩니다.

6. 에 **대상 프레임 워크 변경** 대화 상자, 클릭 **예**합니다.

     프로젝트 닫히고 후 다시 열립니다.

7. 다음이 단계를 수행 하 여 캐싱 어셈블리에 대 한 참조를 추가 합니다.

    1.  **솔루션 탐색기**프로젝트의 이름을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **참조 추가**합니다.

    2.  선택 된 **.NET** 탭을 선택 `System.Runtime.Caching`를 클릭 하 고 **확인**합니다.

#### <a name="to-change-the-target-net-framework-in-a-visual-c-project"></a>Visual C# 프로젝트에서.NET Framework 대상을 변경 하려면

1. **솔루션 탐색기**에서 프로젝트 이름을 마우스 오른쪽 단추로 클릭 하 고 클릭 **속성**합니다.

     응용 프로그램에 대 한 속성 창이 표시 됩니다.

2. **응용 프로그램** 탭을 클릭합니다.

3. 에 **대상 프레임 워크** 목록에서 [!INCLUDE[net_v40_short](../../../../includes/net-v40-short-md.md)]합니다. (선택 하지 마세요 **.NET Framework 4 Client Profile**.)

4. 다음이 단계를 수행 하 여 캐싱 어셈블리에 대 한 참조를 추가 합니다.

    1.  마우스 오른쪽 단추로 클릭 합니다 **참조가** 폴더 및 클릭 한 다음 **참조 추가**합니다.

    2.  선택 된 **.NET** 탭을 선택 `System.Runtime.Caching`를 클릭 하 고 **확인**합니다.

## <a name="adding-a-button-to-the-wpf-window"></a>WPF 창에 단추 추가
 다음으로 단추 컨트롤을 추가 하 고 단추에 대 한 이벤트 처리기를 만듭니다 `Click` 이벤트입니다. 나중에 텍스트 파일의 내용을 캐시 되어 표시 단추를 클릭 하면 되도록 코드를 추가 합니다.

#### <a name="to-add-a-button-control"></a>단추 컨트롤을 추가 하려면

1. **솔루션 탐색기**를 열려는 MainWindow.xaml 파일을 두 번 클릭 합니다.

2. **도구 상자**아래에 있는 **공용 WPF 컨트롤**을 끌어를 `Button` 컨트롤을 `MainWindow` 창.

3. **속성** 창에서 `Content` 의 속성을 `Button` 컨트롤을 **캐시 가져오기**합니다.

## <a name="initializing-the-cache-and-caching-an-entry"></a>캐시를 초기화 하 고 항목 캐싱
 다음으로, 다음 작업을 수행 하는 코드를 추가 합니다.

-   캐시 클래스의 인스턴스를 만들-즉, 인스턴스화 새 <xref:System.Runtime.Caching.MemoryCache> 개체입니다.

-   캐시 사용을 <xref:System.Runtime.Caching.HostFileChangeMonitor> 텍스트 파일에 변경 사항을 모니터링 하는 개체입니다.

-   텍스트 파일을 읽고 캐시 항목으로 해당 콘텐츠를 캐시 합니다.

-   캐시 된 텍스트 파일의 내용을 표시 합니다.

#### <a name="to-create-the-cache-object"></a>캐시 개체를 만들려면

1. MainWindow.Xaml.vb 또는 MainWindow.xaml.cs 파일에 이벤트 처리기를 만들기 위해 방금 추가한 단추를 두 번 클릭 합니다.

2. 클래스 선언) (이전 파일의 맨 위에 있는 다음 코드를 추가 `Imports` (Visual Basic) 또는 `using` 문 (C#):

    ```csharp
    using System.Runtime.Caching;
    using System.IO;
    ```

    ```vb
    Imports System.Runtime.Caching
    Imports System.IO
    ```

3. 이벤트 처리기에서 캐시 개체를 인스턴스화하는 다음 코드를 추가 합니다.

    ```csharp
    ObjectCache cache = MemoryCache.Default;
    ```

    ```vb
    Dim cache As ObjectCache = MemoryCache.Default
    ```

     <xref:System.Runtime.Caching.ObjectCache> 클래스는 메모리 내 개체 캐시를 제공 하는 기본 클래스입니다.

4. 명명 된 캐시 항목의 내용을 다음 코드를 추가 `filecontents`:

    ```vb
    Dim fileContents As String = TryCast(cache("filecontents"), String)
    ```

    ```csharp
    string fileContents = cache["filecontents"] as string;
    ```

5. 라는 캐시 엔트리가 있는지 여부를 확인 하려면 다음 코드를 추가 `filecontents` 존재 합니다.

    ```vb
    If fileContents Is Nothing Then

    End If
    ```

    ```csharp
    if (fileContents == null)
    {

    }
    ```

     지정 된 캐시 엔트리 없으면 텍스트 파일을 읽고 캐시에 캐시 항목으로 추가 해야 합니다.

6. 에 `if/then` 차단 새로 만들려면 다음 코드를 추가 합니다 <xref:System.Runtime.Caching.CacheItemPolicy> 10 초 후에 캐시 엔트리가 만료 되도록 지정 하는 개체입니다.

    ```vb
    Dim policy As New CacheItemPolicy()
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0)
    ```

    ```csharp
    CacheItemPolicy policy = new CacheItemPolicy();
    policy.AbsoluteExpiration = DateTimeOffset.Now.AddSeconds(10.0);
    ```

     기본값은 없습니다 제거 또는 만료 정보를 제공 하는 경우 <xref:System.Runtime.Caching.ObjectCache.InfiniteAbsoluteExpiration>, 절대 시간에만 기반 만료 되지 않도록 캐시 항목을 의미 합니다. 대신, 메모리가 부족 한 경우에 캐시 항목 만료 됩니다. 모범 사례로 항상 명시적으로 절대 또는 상대 (sliding) 만료를 제공 해야 합니다.

7. 내부는 `if/then` 차단 하 고 다음 이전 단계에서 추가한 코드를 모니터링 하 고 컬렉션에 텍스트 파일의 경로 추가 하려면 원하는 파일 경로의 컬렉션을 만드는 다음 코드를 추가 합니다.

    ```vb
    Dim filePaths As New List(Of String)()
    filePaths.Add("c:\cache\cacheText.txt")
    ```

    ```csharp
    List<string> filePaths = new List<string>();
    filePaths.Add("c:\\cache\\cacheText.txt");
    ```

    > [!NOTE]
    >  사용 하려는 텍스트 파일 없으면 `c:\cache\cacheText.txt`, 여기서 텍스트 파일에는 사용 하려는 경로 지정 합니다.

8. 새 추가 하려면 다음 코드를 추가 이전 단계에서 추가한 코드 다음 <xref:System.Runtime.Caching.HostFileChangeMonitor> 캐시 엔트리에 대 한 변경의 컬렉션 개체를 모니터링 합니다.

    ```vb
    policy.ChangeMonitors.Add(New HostFileChangeMonitor(filePaths))
    ```

    ```csharp
    policy.ChangeMonitors.Add(new HostFileChangeMonitor(filePaths));
    ```

     <xref:System.Runtime.Caching.HostFileChangeMonitor> 개체는 텍스트 파일의 경로 모니터링 하 고 변경 될 경우에 캐시를에 알립니다. 이 예제에서는 파일의 내용을 변경 하는 경우 캐시 엔트리가 만료 됩니다.

9. 이전 단계에서 추가한 코드를 다음 텍스트 파일의 내용을 다음 코드를 추가 합니다.

    ```vb
    fileContents = File.ReadAllText("c:\cache\cacheText.txt") & vbCrLf & DateTime.Now.ToString()
    ```

    ```csharp
    fileContents = File.ReadAllText("c:\\cache\\cacheText.txt") + "\n" + DateTime.Now;
    ```

     날짜 및 시간 타임 스탬프는 캐시 항목이 만료 시기를 확인할 수 있도록에 추가 됩니다.

10. 파일의 콘텐츠를 캐시 개체를 삽입할 다음 코드를 추가 다음 이전 단계에서 추가한 코드는 <xref:System.Runtime.Caching.CacheItem> 인스턴스:

    ```vb
    cache.Set("filecontents", fileContents, policy)
    ```

    ```csharp
    cache.Set("filecontents", fileContents, policy);
    ```

     캐시 항목을 전달 하 여 제거 해야 하는 방법에 대 한 정보를 지정 합니다 <xref:System.Runtime.Caching.CacheItemPolicy> 개체를 매개 변수로 만든입니다.

11. 이후에 `if/then` 차단 메시지 상자에 캐시 된 파일의 내용을 표시 하려면 다음 코드를 추가 합니다.

    ```vb
    MessageBox.Show(fileContents)
    ```

    ```csharp
    MessageBox.Show(fileContents);
    ```

12. 에 **빌드** 메뉴에서 클릭 **빌드 WPFCaching** 프로젝트를 빌드해야 합니다.

## <a name="testing-caching-in-the-wpf-application"></a>WPF 응용 프로그램에서 캐싱 테스트
 이제 응용 프로그램을 테스트할 수 있습니다.

#### <a name="to-test-caching-in-the-wpf-application"></a>WPF 응용 프로그램에서 캐싱 테스트

1. Ctrl+F5를 눌러 응용 프로그램을 실행합니다.

     `MainWindow` 창이 표시 됩니다.

2. 클릭 **캐시 가져올**합니다.

     텍스트 파일에서 캐시 된 콘텐츠를 메시지 상자에 표시 됩니다. 파일의 타임 스탬프를 확인 합니다.

3. 메시지 상자를 닫은 다음 클릭 **캐시 가져오기** 다시 합니다.

     타임 스탬프가 변경 되지 않습니다. 이 캐시 된 콘텐츠가 표시 된 것을 나타냅니다.

4. 10 초 이상 기다렸다가 클릭 **캐시 가져오기** 다시 합니다.

     이 이번 새 타임 스탬프로 표시 됩니다. 이 캐시 항목 만료 하도록 정책을 설정 하 고 새 캐시 된 콘텐츠 표시 되도록 나타냅니다.

5. 텍스트 편집기에서 만든 텍스트 파일을 엽니다. 변경 내용을 아직 수행 하지 마십시오.

6. 메시지 상자를 닫은 다음 클릭 **캐시 가져오기** 다시 합니다.

     타임 스탬프를 다시 확인 합니다.

7. 텍스트 파일을 변경 하 고 파일을 저장 합니다.

8. 메시지 상자를 닫은 다음 클릭 **캐시 가져오기** 다시 합니다.

     이 메시지 상자 텍스트 파일 및 새 타임 스탬프에서 업데이트 된 콘텐츠를 포함합니다. 이 호스트 파일 변경 모니터의 캐시 엔트리를 제거는 파일을 변경 하는 경우에 즉시 절대 제한 시간 만료 되지 않은 경우에 나타냅니다.

    > [!NOTE]
    >  제거 시간 20 초 이상으로 변경 하는 파일의 수에 대 한 더 많은 시간을 늘릴 수 있습니다.

## <a name="code-example"></a>코드 예제
 이 연습을 완료 한 후 방금 만든 프로젝트에 대 한 코드를 다음 예와 비슷하게 표시 됩니다.

 [!code-csharp[CachingWPFApplications#1](~/samples/snippets/csharp/VS_Snippets_Wpf/CachingWPFApplications/CSharp/MainWindow.xaml.cs#1)]
 [!code-vb[CachingWPFApplications#1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/CachingWPFApplications/VisualBasic/MainWindow.xaml.vb#1)]

## <a name="see-also"></a>참고자료

- <xref:System.Runtime.Caching.MemoryCache>
- <xref:System.Runtime.Caching.ObjectCache>
- <xref:System.Runtime.Caching>
- [.NET Framework 애플리케이션에서 캐시](../../performance/caching-in-net-framework-applications.md)
