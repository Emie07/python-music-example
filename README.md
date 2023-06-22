# python-music-example
A simple music python code edit 

import lyricsgenius

def search_lyrics(song_name):
    # 你需要在 Genius.com 上注册一个账户，并获取 API 访问令牌
    # 将你的访问令牌替换为下面的 'YOUR_ACCESS_TOKEN' 字符串
    genius = lyricsgenius.Genius('YOUR_ACCESS_TOKEN')

    try:
        # 通过歌曲名称搜索歌词
        song = genius.search_song(song_name)
        
        if song is not None:
            # 返回歌词文本
            return song.lyrics
        else:
            return "找不到该歌曲的歌词。"

    except Exception as e:
        print("出现错误：", e)
        return "获取歌词时发生错误。"

# 示例用法
song_name = input("请输入歌曲名称：")
lyrics = search_lyrics(song_name)
print(lyrics)

# As reminder - "pip install lyricsgenius" need to be installed 
