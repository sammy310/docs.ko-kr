---
title: My.Forms 개체 (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- My.Forms
- My.MyProject.Forms
helpviewer_keywords:
- My.Forms object
ms.assetid: f6bff4e6-6769-4294-956b-037aa6106d2a
ms.openlocfilehash: 4998097b910a504461a34af3cc159ddb1c74cc62
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "61949320"
---
# <a name="myforms-object"></a>My.Forms 개체
현재 프로젝트에 선언 된 각 Windows form의 인스턴스에 액세스 하기 위한 속성을 제공 합니다.  
  
## <a name="remarks"></a>설명  
 `My.Forms` 개체는 현재 프로젝트에 각 형식의 인스턴스를 제공 합니다. 속성의 이름 속성에 액세스 하는 형식의 이름으로 동일 합니다.   
  
 제공한 폼에 액세스할 수 있습니다는 `My.Forms` 한정자 없이 폼의 이름을 사용 하 여 개체입니다. 폼의 형식 이름과 속성 이름 이므로 이렇게 하면 기본 인스턴스가 처럼 폼에 액세스할 수 있습니다. 예를 들어 `My.Forms.Form1.Show`은 `Form1.Show`와 같습니다.  
  
 `My.Forms` 개체는 현재 프로젝트와 연결 된 폼만 표시 합니다. 참조 되는 Dll에 선언 된 폼에 대 한 액세스를 제공 하지 않습니다. DLL을 제공 하는 폼에 액세스 하려면 기록 폼의 정규화 된 이름을 사용 해야 합니다 *DllName*. *FormName*합니다.  
  
 사용할 수는 <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A> 속성을 모든 응용 프로그램의 열려 있는 폼의 컬렉션을 가져옵니다.  
  
 개체 및 해당 속성은 Windows 응용 프로그램에만 사용할 수 있습니다.  
  
## <a name="properties"></a>속성  
 각 속성은 `My.Forms` 개체는 현재 프로젝트에 폼의 인스턴스에 대 한 액세스를 제공 합니다. 속성의 이름은 속성이 액세스 하는 폼의 이름과 동일 하 고 속성 형식은 폼의 형식과 동일 합니다.  
  
> [!NOTE]
>  이름이 충돌할 경우 양식에 액세스 하려면 속성 이름이 *RootNamespace*_*Namespace*\_*FormName*합니다. 예를 들어 이라는 두 개의 폼 `Form1.`루트 네임 스페이스의 경우 이러한 형식 중 하나 `WindowsApplication1` 및 네임 스페이스 `Namespace1`를 통해 해당 폼에 액세스 하면 `My.Forms.WindowsApplication1_Namespace1_Form1`.  
  
 `My.Forms` 개체는 시작 시 생성 된 응용 프로그램의 주 폼의 인스턴스에 대 한 액세스를 제공 합니다. 다른 모든 폼에 대해는 `My.Forms` 개체에 액세스 하 고 저장 하는 경우 폼의 새 인스턴스를 만듭니다. 폼의 해당 인스턴스를 반환 하는 이후에 해당 속성에 액세스 하려고 시도 합니다.  
  
 할당 하 여 폼의 삭제할 수 있습니다 `Nothing` 해당 형식에 대 한 속성입니다. 속성 setter 호출을 <xref:System.Windows.Forms.Form.Close%2A> 폼과 다음 할당 방법을 `Nothing` 저장 된 값입니다. 이외의 모든 값을 할당 하는 경우 `Nothing` 속성에 setter throw는 <xref:System.ArgumentException> 예외입니다.  
  
 속성이 있는지 여부를 테스트할 수 있습니다 합니다 `My.Forms` 개체를 사용 하 여 형식의 인스턴스를 저장 합니다 `Is` 또는 `IsNot` 연산자입니다. 이러한 연산자를 사용 하 여 속성의 값이 인지 확인 하려면 `Nothing`합니다.  
  
> [!NOTE]
>  일반적으로 `Is` 또는 `IsNot` 연산자의 비교를 수행 하는 속성의 값을 읽을 수 있습니다. 그러나 현재 저장 하는 경우 `Nothing`, 속성 형식의 새 인스턴스를 만들고 다음 해당 인스턴스를 반환 합니다. Visual Basic 컴파일러의 속성을 처리 하는 반면 합니다 `My.Forms` 다르게 개체를 허용 합니다 `Is` 또는 `IsNot` 해당 값을 변경 하지 않고 속성의 상태를 확인 하는 연산자.  
  
## <a name="example"></a>예제  
 이 예제에서는 기본 제목을 변경 `SidebarMenu` 폼입니다.  
  
 [!code-vb[VbVbalrMyForms#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyForms/VB/Class1.vb#2)]  
  
 이 예제가 작동 하려면 프로젝트가 있어야 라는 폼을 `SidebarMenu`입니다.  
  
 이 코드는 Windows 응용 프로그램 프로젝트에만 작동 합니다.  
  
## <a name="requirements"></a>요구 사항  
  
### <a name="availability-by-project-type"></a>프로젝트 형식에 따라 가용성  
  
|프로젝트 형식|사용 가능|  
|---|---|  
|Windows 애플리케이션|**예**|  
|클래스 라이브러리|아니요|  
|콘솔 애플리케이션|아니요|  
|Windows 컨트롤 라이브러리|아니요|  
|웹 컨트롤 라이브러리|아니요|  
|Windows 서비스|아니요|  
|웹 사이트|아니요|  
  
## <a name="see-also"></a>참고자료

- <xref:Microsoft.VisualBasic.ApplicationServices.WindowsFormsApplicationBase.OpenForms%2A>
- <xref:System.Windows.Forms.Form>
- <xref:System.Windows.Forms.Form.Close%2A>
- [개체](../../../visual-basic/language-reference/objects/index.md)
- [Is 연산자](../../../visual-basic/language-reference/operators/is-operator.md)
- [IsNot 연산자](../../../visual-basic/language-reference/operators/isnot-operator.md)
- [응용 프로그램 폼 액세스](../../../visual-basic/developing-apps/programming/accessing-application-forms.md)
