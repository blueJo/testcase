
һ��������װ
1����װLibrary
pip install robotframework  (VERSION = '2.9.1')
pip install --upgrade robotframework-httplibrary
pip install requests  (VERSION = '2.9.1')
pip install -U robotframework-requests (VERSION = '0.3.8')
pip install robotframework-databaselibrary
pip install PyMySQL
2�����ÿ�
Library HttpLibrary.HTTP
Library RequestsLibrary
Library Collections
Library DatabaseLibrary
 
��������������ͽ����ʽ
1�����Ա�����������(Windowsϵͳ�д��ڣ�Linux������)
�޸�C:\Python27\Lib\site-packages\robot\utils\encodingsniffer.py  
�޸�ǰ��
DEFAULT_SYSTEM_ENCODING = 'cp125'
DEFAULT_OUTPUT_ENCODING = 'cp437'
�޸ĺ�
DEFAULT_SYSTEM_ENCODING = 'cp936'
DEFAULT_OUTPUT_ENCODING = 'cp936'
2��HttpLibrary ����http���󱨴�ascii codec can't decode byte 0xe8 in position 0:ordinal not in range(128)
�޸�HttpLibrary����init.py ��������£�
import sys
reload(sys)
sys.setdefaultencoding('utf-8')
 
3����� requestlibrary  tojson  �����޷�������ʾ������
�޸�  ��Ӳ��� ensure_ascii=False,
     def _json_pretty_print(self, content):
        """ Pretty print a JSON object
        'content'  JSON object to pretty print
        """
        temp = json.loads(content)
        return json.dumps(
            temp,
            ensure_ascii=False,
            sort_keys=True,
            indent=4,
            separators=(
                ',',
                ': '))