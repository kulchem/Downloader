# Downloader
public class HEde {
    public static void main(String[] args) throws Exception
    {
        URL u = new URL("https://r13---sn-p5qlsned.googlevideo.com/videoplayback?nh=IgpwcjAxLmlhZDA3KgkxMjcuMC4wLjE&source=youtube&dur=189.196&lmt=1434566950218520&key=yt5&ipbits=0&requiressl=yes&fexp=901816%2C923607%2C9408142%2C9408420%2C9408710%2C9408737%2C9415327%2C9416126%2C9416327%2C9416530%2C9416729&id=o-AE3DVG5_xQf5IwYdESZBDDVSOtd3hIL_0o5hsnx5e9QF&sver=3&mm=31&mn=sn-p5qlsned&mt=1436361908&mv=m&initcwndbps=4048750&ms=au&itag=36&upn=f6KcvbcXamY&sparams=dur%2Cid%2Cinitcwndbps%2Cip%2Cipbits%2Citag%2Clmt%2Cmime%2Cmm%2Cmn%2Cms%2Cmv%2Cnh%2Cpl%2Crequiressl%2Csource%2Cupn%2Cexpire&mime=video%2F3gpp&pl=32&ip=2001%3A4802%3A7803%3A104%3Abe76%3A4eff%3Afe20%3Ab1cf&expire=1436383616&signature=D8C907BFC40D1F35117E20BEB0194AD763D9578E.88A8845D5C2B215D0F69B5A4C85AA41A51608AFE&ratebypass=yes&title=NBA+Live+2016+Kibar+Feyzo+M+zi+i");
        URLConnection uc = u.openConnection();
        System.out.println(uc.getHeaderFields());
        InputStream is = uc.getInputStream();
        long toplamInen = 0;
        long toplamBoyut = uc.getContentLengthLong();
        
        FileOutputStream fos = new FileOutputStream(new File("aaaa.exe"));
        
        is.skip(toplamInen);
        
        byte[] chunk = new byte[2048];
        
        int okunan = 0;
        while ( (okunan = is.read(chunk)) != -1)
        {
            toplamInen += okunan;
            System.out.println(toplamInen);
            fos.write(chunk, 0, okunan);
        }
        
        fos.close();
    }
}
