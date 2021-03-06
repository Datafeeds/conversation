---

copyright:
  years: 2015, 2018
lastupdated: "2018-02-13"

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}
{:tip: .tip}
{:pre: .pre}
{:codeblock: .codeblock}
{:screen: .screen}
{:javascript: .ph data-hd-programlang='javascript'}
{:java: .ph data-hd-programlang='java'}
{:python: .ph data-hd-programlang='python'}
{:swift: .ph data-hd-programlang='swift'}

# 使用交談
{: #logs_convo}

若要開啟使用者與工作區之間互動的清單，請選取導覽列中**使用者交談**。如果看不到**使用者交談**，請使用 ![功能表](images/Menu_16.png) 功能表來開啟頁面。
{: shortdesc}

當您開啟**使用者交談**頁面時，預設視圖會列出最後一天的結果，最新的結果會先列出。提供訊息中使用的最高目的 (#intent) 和任何辨識到的實體 (@entity) 值，以及訊息文字。針對未辨識的目的，顯示的值是*不相關*。如果未辨識某實體，或尚未提供該實體，則顯示的值是*找不到任何實體*。
![日誌預設頁面](images/logs_page1.png)

請務必注意，**使用者交談**頁面會顯示使用者與工作區之間的*詞語* 總數。詞語是使用者傳送給工作區的單一訊息。每一個交談可能都是由多個詞語所構成。因此，此**使用者交談**頁面上的結果數與[概觀](logs_oview.html)頁面上所顯示的交談次數不同。

## 日誌限制
{: #log-limits}

保留訊息的時間長度，取決於您的 {{site.data.keyword.conversationshort}} 服務方案：

  服務方案                             | 聊天訊息保留
  ------------------------------------ | ------------------------------------
  超值                                 | 過去 90 天
  標準                                 | 過去 30 天
  精簡              | 過去 7 天

## 選取資料來源
{: #select-source}

依預設，**使用者交談**頁面會顯示現行工作區的詞語資料。不過，有時改善具有傳送至實例內其他工作區之詞語的工作區可能十分有用。例如，您可能有多個版本的正式作業工作區及開發工作區；您可以使用相同的詞語資料來改善所有這些工作區。

切換至另一個資料來源時，{{site.data.keyword.conversationshort}} 服務會檢查稱為`部署 ID` 的元素的詞語。「部署 ID」是新增至訊息 API 呼叫的 {{site.data.keyword.conversationshort}} 服務 API 中的唯一 ID。如需將「部署 ID」新增至訊息呼叫的相關資訊，請參閱[跨工作區改善](logs.html#deploy_id)。

若要搭配使用詞語與給定「部署 ID」來移入「改善」區段，請執行下列動作：

1.  選取**資料來源：** ![資料來源鏈結](images/data_source_1.png)
1.  選取部署 ![資料來源鏈結](images/data_source_2.png)
1.  按一下**檢視資料**

現在會顯示選取的資料來源。

**附註：**雖然**資料來源：**現在會顯示用來改善此工作區的詞語來源，但是頁面頂端仍然會顯示您將套用變更的工作區。

在此範例中，「改善」頁面會移入將部署 ID `HelpDesk-Production` 內含在其訊息 API 呼叫中的詞語，但是，如果按一下**儲存**將詞語*測試輸入* 新增至目的 **#No**，則會在工作區 `HelpDesk-Development` 中將*測試輸入* 新增為 `#No` 範例。
![資料來源鏈結](images/data_source_3.png)

## 過濾詞語

您可以依*搜尋使用者陳述式*、*目的*、*實體* 及*過去* n * 天* 來過濾詞語：

*搜尋使用者陳述式* - 在搜尋列中鍵入字組。這會搜尋使用者的輸入，但不會搜尋工作區的回覆。

*目的* - 選取下拉功能表，然後在輸入欄位中鍵入目的，或從移入的清單中進行選擇。您可以選取多個目的，以使用任何選取的目的來過濾結果（包括*不相關*）。

![「目的」下拉功能表](images/intents_filter.png)

*實體* - 選取下拉功能表，然後在輸入欄位中鍵入實體名稱，或從移入的清單中進行選擇。您可以選取多個實體，以依任何選取的實體來過濾結果。如果您依目的*及* 實體過濾，則結果將包含具有這兩個值的訊息。您也可以使用*找不到任何實體* 來過濾結果。

![「實體」下拉功能表](images/entities_filter.png)

詞語可能需要一些時間進行更新。在使用者與工作區進行互動之後，請至少等待 30 分鐘，再嘗試過濾該內容。

## 檢視個別詞語
您可以展開每一個詞語項目，以查看使用者在整個交談中提到的內容，以及工作區如何回答。若要這麼做，請選取**開啟交談**。會自動將您帶到您在該交談內選取的詞語。

![「開啟交談」畫面](images/open_convo.png)

然後，您可以選擇顯示所選取詞語的分類。

![具有分類的「開啟交談」畫面](images/open_convo_classes.png)

## 更正目的

1.  若要更正目的，請選取所選擇 #intent 旁的 ![編輯](images/edit_icon.png) 編輯圖示。
1.  從提供的清單中，選取此輸入的正確目的。
    - 開始在輸入欄位中鍵入，並過濾目的清單。
    - 您也可以從此功能表中選擇**標示為不相關**。（如需相關資訊，請參閱[標示為不相關](intents.html#mark-irrelevant)。）或者，您可以選擇**不對目的進行訓練**，這不會儲存此詞語作為訓練的範例。

    ![選取目的](images/select_intent.png)
1.  選取**儲存**。

    ![儲存目的](images/save_intent.png)

    **附註**：{{site.data.keyword.conversationshort}} 服務支援將使用者輸入以範例形式*依現狀* 新增至目的。如果您要在目的訓練資料中以範例形式使用 @entity 參照，而且您要儲存的使用者詞語包含訓練資料中的實體值或同義字，則稍後必須編輯詞語。儲存之後，請從「目的」頁面中編輯詞語，以取代它所參照的實體。如需相關資訊，請參閱[將 @Entity 直接參照為目的範例](intents.html#entity-as-example)。

## 新增實體值或同義字

1.  若要新增實體值或同義字，請選取所選擇 @entity 旁的 ![編輯](images/edit_icon.png) 編輯圖示。
1.  選取**新增實體**。

    ![新增實體](images/add_entity.png)
1.  現在，選取畫底線的使用者輸入中的字組或詞組。

    ![選取實體](images/select_entity.png)
1.  選擇將所強調顯示的詞組作為值新增至其中的實體。
    - 開始在輸入欄位中鍵入，並過濾實體及值清單。
    - 若要新增所強調顯示的詞組作為現有值的同義字，請從下拉清單中選擇 `@entity:value`。

    ![新增實體字組](images/add_entity_word.png)
1.  選取**儲存**。

    ![儲存實體](images/add_entity_save.png)
