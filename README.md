static void Main(string[] args)

{
	InitPlayerInfo();
    InitStore();
    
    while (true)
    {
    	// 1: 상태 보기, 2: 인벤토리, 3: 상점
        if (startState == 0) DisplayStartState();
        else if (startState == 1) DisplayPlayerInfo();
        else if (startState == 2) DisplayInventoryInfo();
        else DisplayStore();
    }
    // 플레이어 닉네임을 받아서 플레이어 객체 생성
// 초기값을 설정해줌
static void InitPlayerInfo()
{
	Console.Title = "[ 스파르타 던전 ]";
    Console.WriteLine("[ 스파르타 던전 ]");
    Console.WriteLine();
    Console.Write("ZEUS 닉네임을 입력해주세요 : ");
    string playerName = Console.ReadLine();
    player = new Player(playerName, PLAYER_HP, PLAYER_SHIELD, PLAYER_POWER, PLAYER_MONEY, new List<Item>());
    
    player.InitItemList(GetItemFromDB(0));
    player.InitItemList(GetItemFromDB(1));
    player.InitItemList(GetItemFromDB(3));
}
}
// 플레이어 닉네임을 받아서 플레이어 객체 생성
// 초기값을 설정해줌
static void InitPlayerInfo()
{
	Console.Title = "[ 스파르타 던전 ]";
    Console.WriteLine("[ 스파르타 던전 ]");
    Console.WriteLine();
    Console.Write("ZEUS 닉네임을 입력해주세요 : ");
    string playerName = Console.ReadLine();
    player = new Player(playerName, PLAYER_HP, PLAYER_SHIELD, PLAYER_POWER, PLAYER_MONEY, new List<Item>());
    
    player.InitItemList(GetItemFromDB(0));
    player.InitItemList(GetItemFromDB(1));
    player.InitItemList(GetItemFromDB(3));
}
static void DisplayStartState()
{
	Console.Clear();
    Console.WriteLine("스파르타 마을에 오신 여러분 환영합니다.");
    Console.WriteLine("이곳에서 던전으로 들어가기 전 활동을 할 수 있습니다.");
    Console.WriteLine();
    ("1").PrintWithColor(ConsoleColor.Magenta, false);
    Console.WriteLine(". 상태 보기");
    ("2").PrintWithColor(ConsoleColor.Magenta, false);
    Console.WriteLine(". 인벤토리");
    ("3").PrintWithColor(ConsoleColor.Magenta, false);
    Console.WriteLine(". 상점");
    Console.WriteLine();
    startState = GetPlayerSelect(1, 3);

    // 시작 화면에서 상태 보기 선택시 실행
// 화면에 플레이어의 정보 표시
// 레벨, 이름, 직업, 공격력, 방어력, 체력, Gold
static void DisplayPlayerInfo()
{
	Console.Clear();
    ("상태 보기").PrintWithColor(ConsoleColor.Yellow, true);
    Console.WriteLine("캐릭터의 정보가 표시됩니다.");
    Console.WriteLine();
    
    player.DisplayPlayerInfo();
    Console.WriteLine(); Console.WriteLine();
    
    ("0").PrintWithColor(ConsoleColor.Magenta, false); Console.WriteLine(". 나가기");
    Console.WriteLine();
    
    int select = GetPlayerSelect(0, 0);
    if (select == 0) startState = select;
}
}
